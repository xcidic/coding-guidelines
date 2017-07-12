---
title: "NodeJS Style Guide"
date: 2017-07-12T14:18:35+07:00
draft: false
weight: 2
---

## Node.JS: Style and structure

### Additional JavaScript style guides

*   [Felix's Node.js Style Guide](http://nodeguide.com/style.html)
*   Crockford's [Code Conventions for the JavaScript Programming Language](http://javascript.crockford.com/code.html)
*   Or, for something a little more unconventional: [NPM's Coding Style](https://docs.npmjs.com/misc/coding-style)
* Define in this docs

## Table of Contents

1. [Avoid this and new](#avoid-this-and-new)
1. [More, smaller functions](#more-smaller-functions)
1. [Consistently asynchronous APIs](#consistently-asynchronous-apis)
1. [Always check for errors in callbacks](#always-check-for-errors-in-callbacks)
1. [Return on callbacks](#return-on-callbacks)
1. [Only throw in synchronous functions](#only-throw-in-synchronous-functions)
1. [Catch errors in sync calls](#catch-errors-in-sync-calls)
1. [Stick to the callback convention](#stick-to-the-callback-convention)
1. [Wrap up](#wrap-up)

## Avoid this and new

This may seem like quibbling over coding style, but in Node.js it's an important way of keeping your functions easily composable and reusable.

Because Node.js involves passing around many callbacks and using a lot of higher-level functions to manage control flow; you should make sure functions are easy to move around without having to bind to a specific context. Prefer closures over object methods, and prefer explicit arguments over closures.

```javascript
// contrived example using prototypes and 'this'

function DB(url) {
    this.url = url;
}

DB.prototype.info = function (callback) {
    http.get(this.url + '/info', callback);
};

async.parallel([
    function (cb) {
        new DB('http://foo').info(cb);
    },
    function (cb) {
        new DB('http://bar').info(cb);
    }
], ...);


// similar example using closures

function DB(url) {
    return { info: async.apply(http.get, url + '/info') };
}

async.parallel([
    DB('http://foo').info,
    DB('http://bar').info
], ...);


// making all arguments explicit

var dbInfo = function (url, callback) {
    http.get(url + '/info', callback);
};

async.map(['http://foo', 'http://bar'], dbInfo, ...);
```

The final style, with all arguments made explicit, allows us to easily pass in an arbitrary list of URLs and perform the same operation on them all. Using a more functional style will make your life significantly easier when it comes to combining functionality in this way.

Of course, there are cases where making all arguments explicit would be undesirable, and cases where using constructors and prototypes are more efficient. I simply recommend you prefer the latter styles over the former and justify your use of these features when necessary.

## More, smaller functions

Before you even start looking into control flow libraries like async, you can tame much of the "callback hell" by simply breaking up your functions into smaller components.

```javascript
// a deeply-nested function including four asynchronous operations

function convertJsonToCsv(filename, target, callback) {
    readFile(filename, function (err, content) {
        if (err) {
            return callback(err);
        }
        parseJson(content, function (err, data) {
            if (err) {
                return callback(err);
            }
            convertToCsv(data, function (err, csv) {
                if (err) {
                    return callback(err);
                }
                writeFile(target, csv, callback);
            });
        });
    });
}


// the same functionality broken into smaller parts

function convertJsonToCsv(filename, target, callback) {
    readJsonFile(filename, function (err, data) {
        if (err) {
            return callback(err);
        }
        writeCsvFile(target, data, callback);
    });
}

function readJsonFile(filename, callback) {
    readFile(filename, function (err, content) {
        if (err) {
            return callback(err);
        }
        parseJson(content, callback);
    });
}

function writeCsvFile(target, data, callback) {
    convertToCsv(data, function (err, csv) {
        if (err) {
            return callback(err);
        }
        writeFile(target, csv, callback);
    });
}
```

I'd recommend you try and keep your functions down to two asynchronous operations at a time, as in the above example, or to one iteration over a list (using async.map or similar). Having more, smaller functions also makes it easier to recombine them in new ways later on.

Of course, you can further clean up your code using an asynchronous control flow library. But this is the first step in getting things readable again.

## Consistently asynchronous APIs

In order to keep your code predictable, a function should be either always asynchronous, or always synchronous. Consider the following:

```javascript
var CACHE = {};

function getRecord(id, callback) {
    if (CACHE[id]) {
        return CACHE[id];
    }
    http.get('http://foo/' + id, callback);
}
```

When someone attempts to use this function, it's very easy to miss out the cached case and have code that never completes:

```javascript
function getMyRecord(user, callback) {
    getRecord('record-' + user.id, callback);
}
```

The first time you call getMyRecord it will complete successfully, the second time it will never call the callback (because getRecord returns immediately with the cached result). This might halt execution of the request.

Another concern with the getRecord function is execution order:

```javascript
function getMyRecord(user, callback) {
    var r = getRecord('record-' + user.id, function (err, record) {
        if (record) {
            record.got = true;
        }
        return callback(err, record);
    });
    if (r) {
        r.got = true;
    }
    return r;
}
```

Code like this is just too difficult to reason about. In order to implement it reliably you'd have to duplicate code inside the getRecord callback, and after it (in case it's synchronous). You then have to do the same thing any time you call the getMyRecord function too. This very quickly becomes messy and confusing.

The correct way to handle this is to use process.nextTick to make getRecord asynchronous even when returning a cached result:

```javascript
var CACHE = {};

function getRecord(id, callback) {
    if (CACHE[id]) {
        return process.nextTick(function () {
            return callback(null, CACHE[id]);
        });
    }
    http.get('http://foo/' + id, callback);
}
```

Now we need only consider the asynchronous case and our code becomes much more predictable.

## Always check for errors in callbacks

Missing an error check inside a callback is a common cause of confusion in debugging. The problem is that the program execution will continue and the failure may manifest itself elsewhere in the code and give you a different error message. You then have to trace it back to the original location.

Failing to explicitly check for errors inside a callback should be considered a bug. I highly recommend you build this step into your code review process because it can be so easy to miss.

```javascript
// wrong!

function writeCsvFile(target, data, callback) {
    convertToCsv(data, function (err, csv) {
        writeFile(target, csv, callback);
    });
}


// right

function writeCsvFile(target, data, callback) {
    convertToCsv(data, function (err, csv) {
        if (err) {
            return callback(err);
        }
        writeFile(target, csv, callback);
    });
}
```

If you want to reduce the extra code, you can do a one-line if statement when checking for the error: if (err) return callback(err);. Whichever style you choose, I recommend you are consistent, because this piece of code should be easy to spot and easy to notice when it's missing.

## Return on callbacks

Usually, you call a callback as the last thing you do inside a function. You might consider it synonymous with return, only JavaScript does not halt function execution when it hits it. It can be easy to accidentally let execution continue after calling a callback, when you really expected it to end. In order to make this easy to spot, and make sure execution stops in the way you expect, I recommend returning the callback function call.

```javascript
// wrong!

function writeCsvFile(target, data, callback) {
    convertToCsv(data, function (err, csv) {
        if (err) {
            callback(err); // oops! no return
        }
        // this line gets called even when theres an error
        writeFile(target, csv, callback);
    });
}


// right

function writeCsvFile(target, data, callback) {
    convertToCsv(data, function (err, csv) {
        if (err) {
            return callback(err); // execution stops here
        }
        writeFile(target, csv, callback);
    });
}
```

## Only throw in synchronous functions

Unfortunately, you can't use try-catch blocks around asynchronous code. That means any exceptions you throw will not be caught and bubble up to the top. This can kill your entire server process if you don't have an uncaughtException handler set up. Even in cases where you do, the error probably no longer has any meaningful context and you can't appropriately respond to a http request, for example.

Always, always, always pass errors back to the callback in asynchronous functions. As long as you're following the "Always check for errors in callbacks" rule the errors will be handled in the appropriate place.

```javascript
// wrong!

function getRecord(id, callback) {
    http.get('http://foo/' + id, function (err, doc) {
        if (err) {
            return callback(err);
        }
        if (doc.deleted) {
            // this will not get caught by the function calling getRecord
            throw new Error('Record has been deleted');
        }
        return callback(null, doc);
    });
}

// right

function getRecord(id, callback) {
    http.get('http://foo/' + id, function (err, doc) {
        if (err) {
            return callback(err);
        }
        if (doc.deleted) {
            return callback(new Error('Record has been deleted'));
        }
        return callback(null, doc);
    });
}
```

## Catch errors in sync calls

This is essentially the same as the previous rule. If you're calling a synchronous function that might throw an exception, inside your asynchronous code, then calling your asynchronous code might also result in an exception.

For example:

```javascript
// wrong!

function readJson(filename, callback) {
    fs.readFile(filename, function (err, content) {
        if (err) {
            return callback(err);
        }

        // uh-oh! this line might throw an exception if the content
        // is not valid JSON
        var data = JSON.parse(content.toString());

        return callback(null, data);
    });
}

// right

function readJson(filename, callback) {
    fs.readFile(filename, function (err, content) {
        if (err) {
            return callback(err);
        }
        try {
            var data = JSON.parse(content.toString());
        }
        catch (e) {
            return callback(e);
        }
        return callback(null, data);
    });
}
```

## Stick to the callback convention

There is a vocal minority on the Node.js mailing list and elsewhere which promotes the use of other strategies for handling asynchronous code. Some of them even providing "blocking-style" APIs. While they are interesting, and you might happily use promises or fibers inside your team, please consider sticking to the Node-style callbacks; where the callback is the last argument to an async function and the first argument to the callback is an error (if one occurred).

The vast majority of Node developers follow this style, there is consensus on this. If you expect Node developers outside of your team to use your modules then you'll have a much easier time sticking to convention.

## Wrap up

While most of this is probably common-sense, I hope some of you find these rules useful. Feedback, argument, and further tips are encouraged in the comments.
