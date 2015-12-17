---
layout: default
section: expressions
title: "ROUNDUP"
description: "Rounds a number up to a desired number of decimal places."
category: section
permalink: /expressions/reference/roundup/
---

## ROUNDUP

Rounds a number up to a desired number of decimal places.

### Parameters

`value` Number (__required__) - The value to round up.

`places` Number (__required__) - The number of places to which to round up.

### Returns

Number

### Examples

~~~
ROUNDUP(156.826, 2)

// returns 156.83
~~~
{: .language-js}


~~~
ROUNDUP(156.826, 0)

// returns 157
~~~
{: .language-js}