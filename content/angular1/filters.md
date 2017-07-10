---
title: "Filters"
date: 2017-07-10T18:45:41+07:00
draft: false
weight: 30
---

## Filters

###### [Style [Y420](#style-y420)]

  - Avoid using filters for scanning all properties of a complex object graph. Use filters for select properties.

    *Why?*: Filters can easily be abused and negatively affect performance if not used wisely, for example when a filter hits a large and deep object graph.

**[Back to Table of Contents]({{%relref "angular1/_index.md"%}})**
