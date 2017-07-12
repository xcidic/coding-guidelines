---
title: "Naming"
date: 2017-07-10T18:47:09+07:00
draft: false
weight: 14
---

## Naming

### Naming Guidelines
###### [Style [Y120](#style-y120)]

  - Use consistent names for all components following a pattern that describes the component's feature then (optionally) its type. My recommended pattern is `feature.type.js`. There are 2 names for most assets:
    * the file name (`avengers.controller.js`)
    * the registered component name with Angular (`AvengersController`)

    *Why?*: Naming conventions help provide a consistent way to find content at a glance. Consistency within the project is vital. Consistency with a team is important. Consistency across a company provides tremendous efficiency.

    *Why?*: The naming conventions should simply help you find your code faster and make it easier to understand.

### Feature File Names
###### [Style [Y121](#style-y121)]

  - Use consistent names for all components following a pattern that describes the component's feature then (optionally) its type. My recommended pattern is `feature.type.js`.

    *Why?*: Provides a consistent way to quickly identify components.

    *Why?*: Provides pattern matching for any automated tasks.

  ```javascript
  /**
   * common options
   */

  // Controllers
  avengers.js
  avengers.controller.js
  avengersController.js

  // Services/Factories
  logger.js
  logger.service.js
  loggerService.js
  ```

  ```javascript
  /**
   * recommended
   */

  // controllers
  avengers.controller.js
  avengers.controller.spec.js

  // services/factories
  logger.service.js
  logger.service.spec.js

  // constants
  constants.js

  // module definition
  avengers.module.js

  // routes
  avengers.routes.js
  avengers.routes.spec.js

  // configuration
  avengers.config.js

  // directives
  avenger-profile.directive.js
  avenger-profile.directive.spec.js
  ```

  Note: Another common convention is naming controller files without the word `controller` in the file name such as `avengers.js` instead of `avengers.controller.js`. All other conventions still hold using a suffix of the type. Controllers are the most common type of component so this just saves typing and is still easily identifiable. I recommend you choose 1 convention and be consistent for your team. My preference is `avengers.controller.js` identifying the `AvengersController`.

  ```javascript
  /**
   * recommended
   */
  // Controllers
  avengers.js
  avengers.spec.js
  ```

### Test File Names
###### [Style [Y122](#style-y122)]

  - Name test specifications similar to the component they test with a suffix of `spec`.

    *Why?*: Provides a consistent way to quickly identify components.

    *Why?*: Provides pattern matching for [karma](http://karma-runner.github.io/) or other test runners.

  ```javascript
  /**
   * recommended
   */
  avengers.controller.spec.js
  logger.service.spec.js
  avengers.routes.spec.js
  avenger-profile.directive.spec.js
  ```

### Controller Names
###### [Style [Y123](#style-y123)]

  - Use consistent names for all controllers named after their feature. Use UpperCamelCase for controllers, as they are constructors.

    *Why?*: Provides a consistent way to quickly identify and reference controllers.

    *Why?*: UpperCamelCase is conventional for identifying object that can be instantiated using a constructor.

  ```javascript
  /**
   * recommended
   */

  // avengers.controller.js
  angular
      .module
      .controller('HeroAvengersController', HeroAvengersController);

  function HeroAvengersController() { }
  ```

### Controller Name Suffix
###### [Style [Y124](#style-y124)]

  - Append the controller name with the suffix `Controller`.

    *Why?*: The `Controller` suffix is more commonly used and is more explicitly descriptive.

  ```javascript
  /**
   * recommended
   */

  // avengers.controller.js
  angular
      .module
      .controller('AvengersController', AvengersController);

  function AvengersController() { }
  ```

### Factory and Service Names
###### [Style [Y125](#style-y125)]

  - Use consistent names for all factories and services named after their feature. Use camel-casing for services and factories. Avoid prefixing factories and services with `$`. Only suffix service and factories with `Service` when it is not clear what they are (i.e. when they are nouns).

    *Why?*: Provides a consistent way to quickly identify and reference factories.

    *Why?*: Avoids name collisions with built-in factories and services that use the `$` prefix.

    *Why?*: Clear service names such as `logger` do not require a suffix.

    *Why?*: Service names such as `avengers` are nouns and require a suffix and should be named `avengersService`.

  ```javascript
  /**
   * recommended
   */

  // logger.service.js
  angular
      .module
      .factory('logger', logger);

  function logger() { }
  ```

  ```javascript
  /**
   * recommended
   */

  // credit.service.js
  angular
      .module
      .factory('creditService', creditService);

  function creditService() { }

  // customer.service.js
  angular
      .module
      .service('customerService', customerService);

  function customerService() { }
  ```

### Directive Component Names
###### [Style [Y126](#style-y126)]

  - Use consistent names for all directives using camelCase. Use a short prefix to describe the area that the directives belong (some example are company prefix or project prefix).

    *Why?*: Provides a consistent way to quickly identify and reference components.

  ```javascript
  /**
   * recommended
   */

  // avenger-profile.directive.js
  angular
      .module
      .directive('xxAvengerProfile', xxAvengerProfile);

  // usage is <xx-avenger-profile> </xx-avenger-profile>

  function xxAvengerProfile() { }
  ```

### Modules
###### [Style [Y127](#style-y127)]

  - When there are multiple modules, the main module file is named `app.module.js` while other dependent modules are named after what they represent. For example, an admin module is named `admin.module.js`. The respective registered module names would be `app` and `admin`.

    *Why?*: Provides consistency for multiple module apps, and for expanding to large applications.

    *Why?*: Provides easy way to use task automation to load all module definitions first, then all other angular files (for bundling).

### Configuration
###### [Style [Y128](#style-y128)]

  - Separate configuration for a module into its own file named after the module. A configuration file for the main `app` module is named `app.config.js` (or simply `config.js`). A configuration for a module named `admin.module.js` is named `admin.config.js`.

    *Why?*: Separates configuration from module definition, components, and active code.

    *Why?*: Provides an identifiable place to set configuration for a module.

### Routes
###### [Style [Y129](#style-y129)]

  - Separate route configuration into its own file. Examples might be `app.route.js` for the main module and `admin.route.js` for the `admin` module. Even in smaller apps I prefer this separation from the rest of the configuration.

**[Back to Table of Contents]({{%relref "angular1/_index.md"%}})**
