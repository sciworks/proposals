---
title: Community Testing Bot
layout: proposal
tags: 
 - in-review
---

_Seamless Testing Between Resources_

**Problem**: Open source research projects struggle with project maintaining and automated testing. We cannot easily test on the same systems where the software is used in production.

To solve these problems, we imagine a service that is dually a GitHub bot, and a connector to test infrastructure. The bot component would manage permissions based on GitHub, and both help open source maintainers to triage and organize projects, and also automate the running of tests on external resources. While the permissions model is not yet developed to allow easy access to an HPC cluster, we imagine that someday it could be, or we imagine that centers would be able to use their Kubernetes cluster for this use case. The tool would include a subset of what the Spackbot currently does (interactive messages, issue labeling, assignment), but would be extended to allow configuration with external testing entities, reminders, and would be available for any interested project. Given the low cost, computation wise, of quick API interactions with other online services, it could easily be provided as a community service without extensive costs.

## Use Cases

I have a project that I want to test on multiple resources. Currently, I am limited to the runners offered by my CI service, however
with a community testing bot I can register my repository with the service, and then be able to test on cloud or HPC resources.

## Deliverables

The deliverables for this proposal included:

 1. An app intended to run on a server / cluster that can orchestrate testing
 2. A central GitHub repository for registering or managing runners OR an ability to install the app on a single repository level
 3. Workflows or actions to integrate the two.

## Previous Art

[Prow](https://github.com/kubernetes/test-infra/tree/master/prow) is a prototype for this tool that we imagine. It aids with general triage, organization, and coordination of open source projects on GitHub, and is deployed to Kubernetes, and then acts as an organizational tool and gateway to interact with repository testing. For example:

- Prow is deployed on a Kubernetes cluster
- To enable Prow for a project, a pull request is done to a main repository with configuration and testing specifications.  
- Merging the pull request means that Prow is watching the repository.
- The most minimal usage of Prow is providing automated labeling, maintainer and contributor interactions, and triage robots that use an OWNERS file to assign pull requests and other functionality for PR triage.
- The advanced usage is to add a testing setup to the configuration, meaning what to connect to, how much memory / CPU to use, and what to run. Realistically, we would provide simple templates that a researcher can write some number of commands into for testing.

If there ever could be a permissions model to allow running tests directly on some subset of an HPC system, we want to be ready to support that interaction, and from the most widely used version control platform, GitHub. Prow is already fully developed, and would provide a base model for our design.

## Collaborations

* Research Software Engineers
* HPC Community

## Needs

We likely need a place to deploy a GitHub app, and then a repository root to interact with it 
via workflows.
