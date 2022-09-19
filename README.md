# containerd common project repository

[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/containerd/project/badge)](https://api.securityscorecards.dev/projects/github.com/containerd/project)

This cross-project repository holds utilities, scripts, and common files
used across the containerd core projects and many sub-projects within
the containerd organization.

## release-tool utility

The `release-tool` utility, previously maintained here in the common
project repository, has its own repository now. It is now located in
the [`release-tool`](https://github.com/containerd/release-tool) repo.

## Common scripts

To reduce the need for several copies of tools which perform DCO checks,
file license header checks, and Go vendor compliance, a set of scripts
is maintained here and used within the CI configuration of various
projects within the containerd organization.

The simplest way to see the integration of this common project into a
Travis CI configuration is to look at the example in the
[`containerd/continuity` project here](https://github.com/containerd/continuity/blob/f192d1bf54e8c62a567bd5af21b2bedbb3e8c6d7/.travis.yml#L18-L30).

Common tools are retrieved during `install:` with `go get`, and then
this `containerd/project` repository is cloned in the `before_script:`.
Finally, tools from the `project` repository are then used for checking
DCO signoff, license file headers, and vendoring matching between the
commit and vendor config file.

## Project core documents

Project governance, maintainer list, and contributing guidelines are all
maintained as single copies within this repository and linked to from
all containerd projects to reduce duplication and maintenance across all
repos.

You can see each of these core documents here:
 * [Governance for containerd projects](./GOVERNANCE.md)
 * [Maintainers and reviewers list](./MAINTAINERS)
 * [Contributing guidelines](./CONTRIBUTING.md)

For an example of how to include these in a project's `README.md` file see
the following markdown:
```
## Project details

{Some-project} is a containerd sub-project, licensed under the [Apache 2.0 license](./LICENSE).
As a containerd sub-project, you will find the:
 * [Project governance](https://github.com/containerd/project/blob/main/GOVERNANCE.md),
 * [Maintainers](https://github.com/containerd/project/blob/main/MAINTAINERS),
 * and [Contributing guidelines](https://github.com/containerd/project/blob/main/CONTRIBUTING.md)

information in our [`containerd/project`](https://github.com/containerd/project) repository.
```

### Non-core project documents

If your project is a non-core addition to the containerd GitHub organization, please
make the following changes to your project once approved and added:

 * Clearly state in an opening sentence within your project `README.md` that "_Project X is
 a **non-core** subproject of containerd_"
 * Add the project details boilerplate provided above with the following two changes:
   1. The first line should be modified to state: _{Some-project} is a **non-core** containerd subproject_
   2. Do not link to the core `MAINTAINERS` file in `containerd/project`. That link should be modified to point to your existing non-core project `MAINTAINERS` file.
