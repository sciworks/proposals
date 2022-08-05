---
title: Code Search
layout: proposal
tags: 
 - in-review
---

_Institutional source code search_

This is a proposal to develop an institutional-level website for open source software that
has automated nightly updates and registration.

1. A central repository can hold registration metadata for an organization
2. A central server running on a container cluster watches repositories for nightly changes
3. The current state of the code and metadata is pulled into the interface nightly
4. A branded, professional interface akin to [https://cs.opensource.google/](https://cs.opensource.google/) is updated.

## Use Cases

My organization has many repositories on GitHub, and it's hard to provide an automated,
and easy means to maintain a professional presence for the code, along with an interface
to search and find connections between things. GitHub has search, but it is tends to
be limited and extend beyond the small set of repos you are interested in.

## Deliverables

The deliverables for this proposal include:

 1. A documentation server that provides search and rendering of institutional code.
 2. A GitHub app that connects a central repository to the server
 3. automated workflows to update

Opportunities for extension include supporting other hooks or notifications for the organization repos.

## Collaborations

* Research Software Engineers

## Needs

A container-cluster to run a simple server or app, and a GitHub account to develop
the app, and GitHub workflows, etc.
