---
layout: default
section: expressions
title: "PRECISION"
description: "Returns the precision of a number"
category: section
permalink: /expressions/reference/precision/
---

### Parameters

`value` Number (__required__) - a number

### Returns

Number - the number of decimal places

### Examples

```js
PRECISION(1.333)

// returns 3
```


```js
PRECISION(1.3)

// returns 1
```


```js
PRECISION(1)

// returns 0
```