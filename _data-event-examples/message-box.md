---
layout: default
section: data_events
title: "Verify special choice option"
description: "Use this to warn and confirm that a special choice option was selected"
category: section
tags:
  - validation
  - qa/qc
---

This script checks the value of a choice field for a specific option. If the specific option is chosen, it confirms with the user the intent to select that option. This can be useful if some choice options within a choice field are reserved for special cases where extra precaution might be necessary to prevent accidental entry.

```js
ON('change', 'severity', function (event) {
  if (CHOICEVALUE($severity) === 'Critical') {
    var options = {
      title: 'Warning',
      message: 'You selected a damage severity level of Critical. Are you sure you want to do this?',
      buttons: ['Yes, Critical', 'No']
    };

    MESSAGEBOX(options, function(result) {
      if (result.value !== 'Yes, Critical') {
        // Clear the field if the user answers No
        SETVALUE('severity', null);
      }
    });
  }
})
```
