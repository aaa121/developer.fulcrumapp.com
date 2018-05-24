---
layout: default
section: data_events
title: "SETCHOICEFILTER"
description: "Filter the choices in a choice field or classification field."
category: section
permalink: /data-events/reference/setchoicefilter/
---

### Description

The SETCHOICEFILTER function allows for dynamic filtering of the choice options on choice fields or classification fields. This function differs from [SETCHOICES](/data-events/reference/setchoices/) in that only filters the existing choices. That distinction is important because it allows you to maintain your choice options as choice lists and classification sets with label+value pairs and control the available options from data events without having to completely redefine the options with labels *and* values. Using `SETCHOICEFILTER` you can supply the filter to apply and it will keep the label and values already defined on the choice options. The filtering is applied to the value portion of the choices and uses case-insensitive "contains" comparison.

*NOTE*: SETCHOICEFILTERS() will filter the top level choice options in a classification set.

### Parameters

`field` String (__required__) - The data name for the field

`filter` String,Array,null (__required__) - The string or strings to filter choices by

### Examples

```js
// Filters the choices in the weather summary field to those that contain 'cat'
SETCHOICEFILTER('weather_summary', 'cat');
```


```js
// Filters the choices in the weather summary field to those that contain 'cat' or 'dog'
SETCHOICEFILTER('weather_summary', ['cat', 'dog']);
```


```js
// Unsets any filter previously set by SETCHOICEFILTER and applies no filter
SETCHOICEFILTER('weather_summary', null);
```