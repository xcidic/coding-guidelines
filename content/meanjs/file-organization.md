---
title: "File Organization"
date: 2017-07-12T14:45:04+07:00
draft: false
weight: 3
---

## File Organization

Please do remember the the project name is using prefix `project_`. And if the project name is more than one word use `_` to separate the name, ex: `project_bla_bla`, `project_abc`.
Always build a master css file which include styles for every modules.
Always build a module-specific css file for styles only used in said module.

- Deliverables

  Please remove legacy files, be certain the work is delivered in a clean file system, and in an orderly, logical structure that serves a clear purpose.

- Folder Structure

  For every module will use this kind of folder structure. Module name will use lower case. If the module name consist more than one word, use ‘-’ to separate for each word.

### Normal module will consist of these folder:

* `client` - Front end related files, consist of
    1. `config`

        This folder is used to put menu config and routing states.

    2. `controllers`

        This folder is used to put all the controller. Please separate controllers between views.

    3. `css`

        This folder is used to put css for this module if there is any. This folder is optional.

    4. `directives`

        This folder is used to put directives for this module if there is any. This folder is optional.

    5. `img`

        This folder is used to put images for this module if there is any. This folder is optional.
    6. `services`

        This folder is used to put the services.

    7. `views`
        This folder is used to put all the views. Please remind that for ERP project we will only use two views: list and modify (modify is one view used for create, edit and view).

    8. `[module-name].client.module.js`

        This file is used for register modules with services, routes, and/or external modules.


* `server` - Back end related files
    1. `config`

        This folder is used for initializing and declare module dependencies.

    2. `controllers`

        This folder is used for query to database with using mongoosejs.

    3. `models`

        This folder is used for declaring model that will be used in database.
    4. `policies`

        This folder is used for declaring permission for API resources.
    5. `routes`

    This folder is used for declaring route for API.

- Test related files
[TO DO - In development]

### Important Notes

Please do remember that core modules will consist of general functions, directives, css, images and constants that often used by other modules. If the functions, directives, css, images and constants only used by one module, do not put in core module put in these modules instead.
