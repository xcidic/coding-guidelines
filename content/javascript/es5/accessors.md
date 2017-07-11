---
title: "Accessors"
date: 2017-07-11T13:29:09+07:00
draft: false
weight: 50
---

## Accessors

  - Accessor functions for properties are not required.
  - If you do make accessor functions use getVal() and setVal('hello').

    ```javascript
    // bad
    dragon.age();

    // good
    dragon.getAge();

    // bad
    dragon.age(25);

    // good
    dragon.setAge(25);
    ```

  - If the property is a boolean, use isVal() or hasVal().

    ```javascript
    // bad
    if (!dragon.age()) {
      return false;
    }

    // good
    if (!dragon.hasAge()) {
      return false;
    }
    ```

  - It's okay to create get() and set() functions, but be consistent.

    ```javascript
    function Jedi(options) {
      options || (options = {});
      var lightsaber = options.lightsaber || 'blue';
      this.set('lightsaber', lightsaber);
    }

    Jedi.prototype.set = function set(key, val) {
      this[key] = val;
    };

    Jedi.prototype.get = function get(key) {
      return this[key];
    };
    ```

**[⬆ Back to Table of Contents]({{%relref "javascript/es5/_index.md" %}})**
