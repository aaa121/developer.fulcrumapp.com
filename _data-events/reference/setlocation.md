---
layout: default
section: data_events
title: "SETLOCATION"
description: "Set the location of a record."
category: section
permalink: /data-events/reference/setlocation/
---

### Parameters

`latitude` number (__required__) - The new latitude of the record

`longitude` number (__required__) - The new longitude of the record

### Examples

{% highlight js %}
SETLOCATION(35.5946167, -80.8638915)

// Sets the location of a record
{% endhighlight %}