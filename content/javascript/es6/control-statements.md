---
title: "Control Statements"
date: 2017-07-11T16:13:47+07:00
draft: false
weight: 73
---

## Control Statements

  - [17.1](#control-statements) In case your control statement (`if`, `while` etc.) gets too long or exceeds the maximum line length, each (grouped) condition could be put into a new line. It’s up to you whether the logical operator should begin or end the line.

    ```javascript
    // bad
    if ((foo === 123 || bar === 'abc') && doesItLookGoodWhenItBecomesThatLong() && isThisReallyHappening()) {
      thing1();
    }

    // bad
    if (foo === 123 &&
      bar === 'abc') {
      thing1();
    }

    // bad
    if (foo === 123
      && bar === 'abc') {
      thing1();
    }

    // good
    if (
      (foo === 123 || bar === "abc") &&
      doesItLookGoodWhenItBecomesThatLong() &&
      isThisReallyHappening()
    ) {
      thing1();
    }

    // good
    if (foo === 123 && bar === 'abc') {
      thing1();
    }

    // good
    if (
      foo === 123 &&
      bar === 'abc'
    ) {
      thing1();
    }

    // good
    if (
      foo === 123
      && bar === 'abc'
    ) {
      thing1();
    }
    ```

**[⬆ Back to Table of Contents]({{%relref "javascript/es6/_index.md" %}})**
