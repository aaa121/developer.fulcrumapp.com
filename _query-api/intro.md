---
layout: default
section: query_api
order: 1
title: "Query API Introduction"
description: "Introduction to the Fulcrum Query API"
category: section
---

The Query API provides read-only access to interact with your Fulcrum tables and data (records, repeatables, choice lists, members, media, etc.). This endpoint supports most standard [PostgreSQL](https://www.postgresql.org/) database functions, including many advanced spatial types supported by the [PostGIS](http://postgis.net/) extension. This enables real-time data analytics and integrating Fulcrum with a variety of Business Intelligence services and other platforms, as well as programmatically scripting custom data exports.

We currently have two open source repositories on GitHub for working with the Query API:

* [FQ](https://github.com/fulcrumapp/fq) is a Command Line Interface (CLI) built on Node.js. This can be used for programmatically exporting data and scripting custom workflows.
* [Fulcrum Query Utility](https://github.com/fulcrumapp/fulcrum-query-utility) is responsive web application for writing and executing queries and viewing/exporting the returned data.  

## Reference

Check out the full documentation on required parameters, formatting calls, responses and functions by browsing the [Reference](/query-api/reference/) section.

## Functional Examples

We have a [library of examples](/query-api/examples/) available for learning what you can do with the Query API.

## Limitations

- API calls are limited to 5,000 calls an hour per user.
- Queries cannot exceed 10 seconds of processing time to complete.

## SQL Reference Material

 - [SQL Tutorial](http://sqlzoo.net/)
 - [A Primer on SQL](https://leanpub.com/aprimeronsql/read)
 - [Learn SQL the Hard Way](http://sql.learncodethehardway.org/)
 - [A beginners guide to thinking in SQL](http://www.sohamkamani.com/blog/2016/07/07/a-beginners-guide-to-sql/)
 - [PostgreSQL JSON Functions and Operators](https://www.postgresql.org/docs/current/static/functions-json.html)