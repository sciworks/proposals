---
title: Spack Updater
layout: proposal
tags: 
 - developed
---

_spack updater_

For package maintainers in spack, ensuring that a package continues to build with new
versions and other changes in the ecosystem is typically an overlooked problem.
Breaks in builds are typically discovered retroactivelty, meaning that an issue
is opened by a user, and adding new versions is a manual process that can be easily forgotten.

<a href="{{ site.baseurl }}/assets/img/proposals/spack-updater.jpg"><img src="{{ site.baseurl }}/assets/img/proposals/spack-updater.jpg"></a>

> Sketch for design by [@alecbcs](https://github.com/alecbcs)

This project is mostly complete! See [spack-updater](https://github.com/sciworks/spack-updater)
for examples and details.

## Spack Updater

The spack updater will be a simple Python script and GitHub action that is intended to
be deployed in its own repository alongside an organization with one or more spack packages.
As an example, "flux-framework" has several spack packages:

```
fluxbox/    flux-core/  flux-pmix/  flux-sched/
```

And so we could imagine a repository "spack-packages" at `flux-framework/spack-packages`
that handles the following goals.

### Goals

For some number of packages, we want to be able to:

 1. Do a nightly (or otherwise regular build) with spack develop to look for bugs
 2. On new releases of the library:
   a. Retrieve the checksum of the release and add to the spack package file
   b. Perform the new build, and errors are reported immediately to the developer team.
   c. On success, make it easy to contribute the updated package file back to spack.
   
The last step, updating back to spack, will depend on GitHub permissions that are provided
for the runner. A pull personal access token would allow for opening a pull request, however
we likely don't want to give any action that level of permission. Instead, we might have
a workflow in spack that can be given a repository and branch and package name to discover,
and this workflow would retrieve the updated file and open a pull request (within spack).

### Projects Interested

 - [flux-framework](https://github.com/flux-framework/)
 
