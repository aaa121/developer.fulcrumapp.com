---
layout: default
section: data_events
title: "Require captions for a photo field"
description: "Use this custom validation logic to ensure every photo has a caption before saving."
category: section
tags:
  - media events
  - validation
  - qa/qc
---

This example uses the `validate-record` event in conjunction with the [INVALID](/data-events/reference/invalid) function to prevent saving a record if any photos in the `photos` field are missing captions.

```js
ON('validate-record', function (event) {
  // if there are any photos, loop through the $photos objects and test the caption property for null
  if ($photos) {
    for (var i = 0; i < $photos.length; i++) {
      // if caption is missing, alert the user and prevent the record from saving
      if ($photos[i].caption === null) {
        INVALID('All photos must have captions!');
      }
    }
  }
});
```

This can be expanded to look through all photo fields in your app

```js
ON('validate-record', function (event) {
  // loop through the photo fields
  DATANAMES('PhotoField').forEach(function(dataName) {
    // get the photo field value
    var photos = VALUE(dataName);
    // if there are any photos, loop through the photo objects and test the caption property for null
    if (photos) {
      for (var i = 0; i < photos.length; i++) {
        // if caption is missing, alert the user and prevent the record from saving
        if (photos[i].caption === null) {
          INVALID('All photos must have captions!');
        }
      }
    }
  });
});
```
