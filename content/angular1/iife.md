---
title: "IIFE"
date: 2017-07-10T18:45:46+07:00
draft: false
weight: 3
---

## IIFE
### JavaScript Scopes
###### [Style [Y010](#style-y010)]

  - Wrap Angular components in an Immediately Invoked Function Expression (IIFE).

  *Why?*: An IIFE removes variables from the global scope. This helps prevent variables and function declarations from living longer than expected in the global scope, which also helps avoid variable collisions.

  *Why?*: When your code is minified and bundled into a single file for deployment to a production server, you could have collisions of variables and many global variables. An IIFE protects you against both of these by providing variable scope for each file.

  ```javascript
  /* avoid */
  // logger.js
  angular
      .module('app')
      .factory('logger', logger);

  // logger function is added as a global variable
  function logger() { }

  // storage.js
  angular
      .module('app')
      .factory('storage', storage);

  // storage function is added as a global variable
  function storage() { }
  ```

  ```javascript
  /**
   * recommended
   *
   * no globals are left behind
   */

  // logger.js
  (function() {
      'use strict';

      angular
          .module('app')
          .factory('logger', logger);

      function logger() { }
  })();

  // storage.js
  (function() {
      'use strict';

      angular
          .module('app')
          .factory('storage', storage);

      function storage() { }
  })();
  ```

OR…. invocation inside parentheses. This is recomended in **MEANJS**.

  ```
  // logger.js
  (function() {
      'use strict';

      angular
          .module('app')
          .factory('logger', logger);

      function logger() { }
  }());

  // storage.js
  (function() {
      'use strict';

      angular
          .module('app')
          .factory('storage', storage);

      function storage() { }
  }());
  ```

  - Note: For brevity only, the rest of the examples in this guide may omit the IIFE syntax.

  - Note: IIFE's prevent test code from reaching private members like regular expressions or helper functions which are often good to unit test directly on their own. However you can test these through accessible members or by exposing them through their own component. For example placing helper functions, regular expressions or constants in their own factory or constant.

**[Back to Table of Contents]({{%relref "angular1/_index.md"%}})**
