---
title: "Events"
date: 2017-07-11T13:45:09+07:00
draft: false
weight: 52
---

## Events

  - When attaching data payloads to events (whether DOM events or something more proprietary like Backbone events), pass a hash instead of a raw value. This allows a subsequent contributor to add more data to the event payload without finding and updating every handler for the event. For example, instead of:

    ```js
    // bad
    $(this).trigger('listingUpdated', listing.id);

    ...

    $(this).on('listingUpdated', function (e, listingId) {
      // do something with listingId
    });
    ```

    prefer:

    ```js
    // good
    $(this).trigger('listingUpdated', { listingId : listing.id });

    ...

    $(this).on('listingUpdated', function (e, data) {
      // do something with data.listingId
    });
    ```

**[⬆ Back to Table of Contents]({{%relref "javascript/es5/_index.md" %}})**
