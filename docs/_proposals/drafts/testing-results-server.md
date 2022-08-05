---
title: Testing Results Server
layout: proposal
tags: 
 - in-review
---

_Testing Results Server_

There is currently no service that makes it easy to upload, display, and search over testing results. 
Kitware makes a testing platform, [CDash](https://www.kitware.com/cdash/project/about.html) but it requires manual setup and the UI is a bit dated. We imagine a hosted service, with authentication through GitHub, that allows for upload and archive of testing results directly from CI for search and assessment over time.

#### Use Cases

I am a developer at my institution, and I want to be able to track changes in test results over time. I hook my repository up to the institutional test results
server and this provides me API endpoints and interfaces for exploring, visualization, and otherwise interacting with test results.


#### Deliverables

The deliverables for this proposal include:

* A web server intended for uploading and visualizing results
* Actions or other automated means to upload results

#### Collaborations

* Research Software Engineers

#### Needs

Early development can be done on a local machine, however this app will then need to be ported to be accessible from a CI service, so an online resource (e.g., server or container cluster) will be necessary.

