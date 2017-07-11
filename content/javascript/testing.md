---
title: "Testing"
date: 2017-07-11T17:02:10+07:00
draft: false
weight: 84
---

## Testing

  - [29.1](#testing--yup) **Yup.**

    ```javascript
    function foo() {
      return true;
    }
    ```

  - [29.2](#testing--for-real) **No, but seriously**:
    - Whichever testing framework you use, you should be writing tests!
    - Strive to write many small pure functions, and minimize where mutations occur.
    - Be cautious about stubs and mocks - they can make your tests more brittle.
    - We primarily use [`mocha`](https://www.npmjs.com/package/mocha) at Airbnb. [`tape`](https://www.npmjs.com/package/tape) is also used occasionally for small, separate modules.
    - 100% test coverage is a good goal to strive for, even if it’s not always practical to reach it.
    - Whenever you fix a bug, _write a regression test_. A bug fixed without a regression test is almost certainly going to break again in the future.

**[⬆ Back ]({{%relref "javascript/_index.md" %}})**
