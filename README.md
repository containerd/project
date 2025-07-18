# containerd common project repository
This `project` repository contains the governance definitions and specified project
roles like maintainers and security advisors.

## Scripts and utilities

Originally, this repository held common CI scripts/checks as well as the
`release-tool`. Neither of those items are maintained in this repository.
See the below paragraphs for their new locations:

### The release-tool utility

The `release-tool` now has its own repository. It is located in
the [`release-tool`](https://github.com/containerd/release-tool) subproject.

### Common CI checks/scripts

After migrating the entire project and all sub-projects to GitHub
Actions for CI, we made a subproject repo that contains a common `project-checks`
action with our file header, DCO, and vendor checks. That repository is
located in [`project-checks`](https://github.com/containerd/project-checks)

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

If the project has its own `MAINTAINERS` file, that file should contain a comment with a link to
the core `MAINTAINERS` file in `containerd/project` and mention it as additional maintainers.

### Non-core project documents

If your project is a non-core addition to the containerd GitHub organization, please
make the following changes to your project once approved and added:

 * Clearly state in an opening sentence within your project `README.md` that "_Project X is
 a **non-core** subproject of containerd_"
 * Add the project details boilerplate provided above with the following two changes:
   1. The first line should be modified to state: _{Some-project} is a **non-core** containerd subproject_
   2. Do not link to the core `MAINTAINERS` file in `containerd/project`. That link should be modified to point to your existing non-core project `MAINTAINERS` file.
