---
layout: default
section: data_events
title: "SETREADONLY"
description: "Sets a field to be read-only or editable."
category: section
permalink: /data-events/reference/setreadonly/
---

### Parameters

`field` String (__required__) - The data name

`readOnly` boolean,null (__required__) - Boolean value representing whether the field should be read-only, or `null` to restore the original state

### Examples

```js
SETREADONLY('weather_summary', true);

// Sets the field to read only, not editable by the user
```


```js
SETREADONLY('weather_summary', false);

// Sets the field to be active, editable by the user
```


```js
SETREADONLY('weather_summary', null);

// Unsets any override previously set by SETREADONLY and uses the original setting from the form schema
```