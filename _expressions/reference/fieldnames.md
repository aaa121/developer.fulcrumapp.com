---
layout: default
section: expressions
title: "FIELDNAMES"
description: "Returns the child field names of a section or repeatable"
category: section
permalink: /expressions/reference/fieldnames/
---

### Parameters

`dataName` String (__required__) - The data name of the section or repeatable

`options` Object (__required__) - `repeatables` and `sections` boolean values to control whether to drill into further nested sections and repeatables when returning the child fields. For example, passing `{sections: false}` will not return fields that are in nested sections. This function is identical to `FIELDS` except it returns only the data name strings instead of the actual field objects.

### Returns

Array

### Examples

```js
FIELDNAMES('child_items')

// returns ["child_item_cost"]
```