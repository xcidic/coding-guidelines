---
title: "Semicolons"
date: 2017-07-11T16:33:04+07:00
draft: false
weight: 77
---

## Semicolons

  - [21.1](#semicolons--required) **Yup.** eslint: [`semi`](http://eslint.org/docs/rules/semi.html) jscs: [`requireSemicolons`](http://jscs.info/rule/requireSemicolons)

    ```javascript
    // bad
    (function () {
      const name = 'Skywalker'
      return name
    })()

    // good
    (function () {
      const name = 'Skywalker';
      return name;
    }());

    // good, but legacy (guards against the function becoming an argument when two files with IIFEs are concatenated)
    ;((() => {
      const name = 'Skywalker';
      return name;
    })());
    ```

    [Read more](https://stackoverflow.com/questions/7365172/semicolon-before-self-invoking-function/7365214%237365214).

**[⬆ Back to Table of Contents]({{%relref "javascript/es6/_index.md" %}})**
