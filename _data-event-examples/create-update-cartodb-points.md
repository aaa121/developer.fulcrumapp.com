---
layout: default
section: data_events
title: "Update CARTO table from Fulcrum"
description: "Demonstrates how to POST data to the CARTO SQL API."
category: section
tags:
  - request
  - carto
---

This example demonstrates how to build a SQL statement to *create* or *update* records in [CARTO](https://carto.com/). When the Fulcrum record is saved, a POST request is sent to the [CARTO SQL API](https://carto.com/docs/carto-engine/sql-api/). While you can easily sync your Fulcrum app to CARTO via [Data Shares](http://help.fulcrumapp.com/data/what-are-data-shares) and [Synced Tables](https://carto.com/blog/synced-tables-create-real-time-maps-from-data-anywhere/), or write custom [webhooks]({{ site.url }}/general/webhooks/), this method instantly updates your CARTO table without having to wait for a scheduled CARTO sync or even a Fulcrum sync.

```js
var username = 'fulcrum',
  api_key = 'your-carto-api-key',
  type;

ON('new-record', function(event) {
  type = 'create';
});

ON('edit-record', function(event) {
  type = 'update';
});

ON('save-record', function(event) {
  if (type === 'create') {
    query = 'INSERT INTO fulcrum_points_table (fulcrum_id, name, number, color,  the_geom) VALUES ($$' + RECORDID() + '$$, $$' + $name + '$$, ' + $number + ', $$' + STATUS() + '$$, ST_SetSRID(ST_Point(' + LONGITUDE() + ', ' + LATITUDE() + '),4326))';
    postToCarto(query);
  } else if (type === 'update') {
    query = 'UPDATE fulcrum_points_table SET name=$$' + $name + '$$, number=' + $number + ', color=$$' + STATUS() + '$$, the_geom=ST_SetSRID(ST_Point(' + LONGITUDE() + ', ' + LATITUDE() + '),4326) WHERE fulcrum_id=$$' + RECORDID() + '$$';
    postToCarto(query);
  }
});

function postToCarto(query) {
  var options = {
    url: 'https://' + username + '.carto.com/api/v2/sql?q=' + encodeURIComponent(query) + '&api_key=' + api_key,
    method: 'POST'
  };

  REQUEST(options, function(error, response, body) {
    if (error) {
      ALERT('Error with request: ' + INSPECT(error));
    } else {
      ALERT('This record has been successfully posted to CARTO!');
    }
  });
}
```
