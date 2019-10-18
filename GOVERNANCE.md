# containerd Project Governance

As a CNCF member project, we abide by the [CNCF Code of Conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md).

For specific guidance on practical contribution steps for any containerd sub-project please
see our [CONTRIBUTING.md](./CONTRIBUTING.md) guide.

## Maintainership

There are different types of maintainers, with different responsibilities, but
all maintainers have 3 things in common:

1) They share responsibility in the project's success.
2) They have made a long-term, recurring time investment to improve the project.
3) They spend that time doing whatever needs to be done, not necessarily what
is the most interesting or fun.

Maintainers are often under-appreciated, because their work is harder to appreciate.
It's easy to appreciate a really cool and technically advanced feature. It's harder
to appreciate the absence of bugs, the slow but steady improvement in stability,
or the reliability of a release process. But those things distinguish a good
project from a great one.

## Reviewers

A reviewer is a core role within the project.
They share in reviewing issues and pull requests and their LGTM counts towards the
required LGTM count to merge a code change into the project.

Reviewers are part of the organization but do not have write access.
Becoming a reviewer is a core aspect in the journey to becoming a maintainer.

## Adding maintainers

Maintainers are first and foremost contributors that have shown they are
committed to the long term success of a project. Contributors wanting to become
maintainers are expected to be deeply involved in contributing code, pull
request review, and triage of issues in the project for more than three months.

Just contributing does not make you a maintainer, it is about building trust
with the current maintainers of the project and being a person that they can
depend on and trust to make decisions in the best interest of the project.

Periodically, the existing maintainers curate a list of contributors that have
shown regular activity on the project over the prior months. From this list,
maintainer candidates are selected and proposed on the maintainers mailing list.

After a candidate has been announced on the maintainers mailing list, the
existing maintainers are given five business days to discuss the candidate,
raise objections and cast their vote. Votes may take place on the mailing list
or via pull request comment. Candidates must be approved by at least 66% of the
current maintainers by adding their vote on the mailing list. The reviewer role
has the same process but only requires 33% of current maintainers. Only
maintainers of the repository that the candidate is proposed for are allowed to
vote.

If a candidate is approved, a maintainer will contact the candidate to invite
the candidate to open a pull request that adds the contributor to the
MAINTAINERS file. The voting process may take place inside a pull request if a
maintainer has already discussed the candidacy with the candidate and a
maintainer is willing to be a sponsor by opening the pull request. The candidate
becomes a maintainer once the pull request is merged.

## Subprojects

containerd subprojects are divided into two flavors currently: **core** and
**non-core**. Most of the repositories within the containerd GitHub organization are
"core" to the delivery of the containerd runtime project's releases. For example,
the Golang implementations of the cgroups, runc, and console APIs, the ttrpc
implementation, and various built-in plugins like the CRI implementation. These, among a
handful of other repositories, are all **core** and required pieces which culminate
in officially supported and maintained releases of containerd.

Non-core projects have a strong affiliation with the containerd runtime, but
operate similarly to the traditional `contrib/` directory in many open source
projects. In most cases the maintainer list will be unique and the project can
have unique release, support, and maintainer processes. Non-core projects may be
written in other languages and therefore require different skills, developer
tools, and CI systems than the core projects. For these reasons, non-core
subprojects have a few unique properties that are described in the section
"_Adding non-core subprojects_" below.

Both core and non-core subprojects must adhere to the CNCF
[charter](https://www.cncf.io/about/charter/) and mission.

### Adding core subprojects

New core subprojects can request to be added to the containerd GitHub
organization by submitting a project proposal via public forum (a
`containerd/project` GitHub issue is the easiest way to provide this proposal).
The existing maintainers are given five business days to discuss the new
project, raise objections and cast their vote. Projects must be approved by at
least 66% of the current maintainers.

If a project is approved, a maintainer will add the project to the containerd
GitHub organization, and make an announcement on a public forum.

Please add the suggested text from our [Project core documents](./README.md#project-core-documents) section
to your `README.md`.

### Adding non-core subprojects

Non-core subprojects will also submit a project proposal via public forum, and
should state that the project is expected to be **non-core**.

The proposal should include a proposed list of maintainers who will manage
the non-core project and provide general information on support, releases,
stability, and any additional detail useful for the containerd maintainers to
understand the scope and nature of the project.

The existing maintainers are given five business days to discuss the new
project, raise objections and cast their vote. Projects must be approved by at
least 66% of the current maintainers.

If a project is approved, a core maintainer will add the project to the containerd
GitHub organization and provide write access for that repository to the proposed
maintainer list, as well as make an announcement on a public forum.

Unlike core maintainers, non-core project maintainers are responsible for maintenance
tasks in their subproject only. Core maintainers have maintainer privileges across
all core and non-core projects to help contribute to project health, maintenance,
and release processes within the GitHub organization. For ease of list management,
the `MAINTAINERS` file of a non-core project will only list the non-core project
maintainers—the core maintainers of containerd will not be appended to each subproject.

Please add the suggested text from our [Non-core project documents](./README.md#non-core-project-documents)
section to your `README.md`.

## Stepping down policy

Life priorities, interests, and passions can change. If you're a maintainer but
feel you must remove yourself from the list, inform other maintainers that you
intend to step down, and if possible, help find someone to pick up your work.
At the very least, ensure your work can be continued where you left off.

After you've informed other maintainers, create a pull request to remove
yourself from the MAINTAINERS file.

## Removal of inactive maintainers

Similar to the procedure for adding new maintainers, existing maintainers can
be removed from the list if they do not show significant activity on the
project. Periodically, the maintainers review the list of maintainers and their
activity over the last three months.

If a maintainer has shown insufficient activity over this period, a neutral
person will contact the maintainer to ask if they want to continue being
a maintainer. If the maintainer decides to step down as a maintainer, they
open a pull request to be removed from the MAINTAINERS file.

If the maintainer wants to remain a maintainer, but is unable to perform the
required duties they can be removed with a vote of at least 66% of
the current maintainers. An e-mail is sent to the
mailing list, inviting maintainers of the project to vote. The voting period is
five business days. Issues related to a maintainer's performance should be
discussed with them among the other maintainers so that they are not surprised
by a pull request removing them.

## How are decisions made?

containerd is an open-source project with an open design philosophy. This means
that the repository is the source of truth for EVERY aspect of the project,
including its philosophy, design, road map, and APIs. *If it's part of the
project, it's in the repo. If it's in the repo, it's part of the project.*

As a result, all decisions can be expressed as changes to the repository. An
implementation change is a change to the source code. An API change is a change
to the API specification. A philosophy change is a change to the philosophy
manifesto, and so on.

All decisions affecting containerd, big and small, follow the same 3 steps:

* Step 1: Open a pull request. Anyone can do this.

* Step 2: Discuss the pull request. Anyone can do this.

* Step 3: Merge or refuse the pull request. Who does this depends on the nature
of the pull request and which areas of the project it affects.

## Helping contributors with the DCO

The [DCO or `Sign your work`](./CONTRIBUTING.md#sign-your-work)
requirement is not intended as a roadblock or speed bump.

Some containerd contributors are not as familiar with `git`, or have used a web
based editor, and thus asking them to `git commit --amend -s` is not the best
way forward.

In this case, maintainers can update the commits based on clause (c) of the DCO.
The most trivial way for a contributor to allow the maintainer to do this, is to
add a DCO signature in a pull requests's comment, or a maintainer can simply
note that the change is sufficiently trivial that it does not substantially
change the existing contribution - i.e., a spelling change.

When you add someone's DCO, please also add your own to keep a log.

## I'm a maintainer. Should I make pull requests too?

Yes. Nobody should ever push to master directly. All changes should be
made through a pull request.

## Conflict Resolution

If you have a technical dispute that you feel has reached an impasse with a
subset of the community, any contributor may open an issue, specifically
calling for a resolution vote of the current core maintainers to resolve the dispute.
The same voting quorums required (2/3) for adding and removing maintainers
will apply to conflict resolution.
