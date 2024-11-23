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

A reviewer is a core maintainer within the project.
They share in reviewing issues and pull requests and their LGTM counts towards the
required LGTM count to merge a code change into the project.

Reviewers are part of the organization but do not have write access.
Becoming a reviewer is a core aspect in the journey to becoming a committer.

## Committers

A committer is a core maintainer who is responsible for the overall quality and
stewardship of the project. They share the same reviewing responsibilities as
reviewers, but are also responsible for upholding the project bylaws as well as
participating in project level votes.

Committers are part of the organization with write access to all repositories.
Committers are expected to remain actively involved in the project and
participate in voting and discussing of proposed project level changes.

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
maintainer candidates are selected and proposed in the maintainers forum.

After a candidate has been informally proposed in the maintainers forum, the
existing maintainers are given seven days to discuss the candidate, raise
objections and show their support. Formal voting takes place on a pull request
that adds the contributor to the MAINTAINERS file. Candidates must be approved
by 2/3 of the current committers by adding their approval or LGTM to the pull
request. The reviewer role has the same process but only requires 1/3 of current
committers.

If a candidate is approved, they will be invited to add their own LGTM or
approval to the pull request to acknowledge their agreement. A committer will
verify the numbers of votes that have been received and the allotted seven days
have passed, then merge the pull request and invite the contributor to the
organization.

For non-core sub-projects, only committers of the repository that the candidate
is proposed for are given votes.

## Security Advisors

A security advisor is an advisory role in the project responsible for helping
classify and advise on embargoed security disclosures. Security advisors are
individuals trusted by maintainers and representing significant users of the
project.

Security advisors are part of the organization without write access, but with
read access to security disclosures and advisories before becoming public. There
is no expectation of advisors to become reviewers or participate in issue
triage and code review. Security advisors help maintain the integrity of the
security review process and encourage responsible disclosure.

A reviewer may also be a security advisor, however, committers do not need this
role as it is part of their regular duties. The security advisor duties are
not part of the duties of being a reviewer.

Candidates should contact a maintainer and request sponsorship for becoming a
security advisor. Once a maintainer is willing to sponsor a candidate, the
maintainer will open up a pull request to the SECURITY_ADVISORS files adding
the candidate. Since it is not expected that candidates are active in the
project, there is no expectation that they are well known by a majority of
maintainers. Approving the pull request requires a two LGTM threshold of
committers. A reviewer may sponsor themselves, but still require the same two
LGTM threshold of committers.

Security advisors may be removed by the same sponsoring maintainer with a two
LGTM threshold or by any other maintainer with approval of 1/3 of current
committers.

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
The existing maintainers are given seven days to discuss the new project, raise
objections and cast their vote. Projects must be approved by 2/3 of the current
core committers.

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

The existing maintainers are given seven days to discuss the new project, raise
objections and cast their vote. Projects must be approved by 2/3 of the current
core committers.

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

### Changing the status of non-core subprojects

A change of status of a non-core subproject can be made by submitting a change of
status proposal via public forum. The types of changes may include:
- promoting a non-core subproject to core
- removing/archiving the non-core subproject
- merging into another project

The proposal should include some general information on support, releases,
stability, downstream impacts, steps necessary to effect the change, and any
additional detail useful for the containerd maintainers to understand the scope and
nature of the project status change. GitHub issue is the easiest way to provide
this proposal.

The existing maintainers are given fourteen days to discuss the project change,
raise objections and cast their vote. Project changes of this type must be approved
by 2/3 of the current core committers and core committers are encouraged to consider the opinions and objections of the existing non-core project maintainers.

Project status changes do not automatically change the status of any non-core project maintainers.  Project status change proposals may be accompanied by additional proposals to change individual maintainer status, subject to the existing rules set forth in this document.

If a change of status of the non-core subproject is approved, the maintainers will
set forth a schedule for notifying downstream project users, implementing the change
and finally making an announcement on a public forum when the change is complete.

## Stepping down policy

Life priorities, interests, and passions can change. If you're a maintainer but
feel you must remove yourself from the list, inform other maintainers that you
intend to step down, and if possible, help find someone to pick up your work.
At the very least, ensure your work can be continued where you left off.

After you've informed other maintainers, create a pull request to remove
yourself from the MAINTAINERS file.

## Handling inactive maintainers

Similar to the procedure for adding new maintainers, existing maintainers can
be removed from the list if they do not show consistent activity on the
project. Depending on the existing role, committer or reviewer, there are
variations to the inactivity process detailed as follows.

### Committer inactivity process

For committers, the maintainers periodically review committer project
activity. The maintainers use the CNCF "devstats" community metrics tool for
data on user activity statistics.

If a committer has shown no activity over a six-month period, the committer
will be contacted to notify them of their activity status and offer a move to
an Emeritus role. There is no automatic change of status in the project. First,
the activity status is discussed directly with the committer, and second,
maintainers discuss whether other non-tracked contributions to the project
reflect an ongoing, active participation in the project.

Based on the outcome of these discussions, the committer may choose to remove
themselves from the MAINTAINERS file, as noted above in the "Stepping down
policy" section. If another maintainer opens a pull request to the MAINTAINERS
file on their behalf for removal, the PR must be approved by 2/3 of the current
committers, or by the committer who is being removed. The voting and discussion
period is seven days, after which a committer will verify the votes, merge the
pull request, and apply the changes to the organization.

### Reviewer inactivity process

While reviewers are not voting members of the containerd project, the maintainers
may assess reviewer activity periodically and recommend removals for any
completely inactive reviewers.

Reviewers may remove themselves from the MAINTAINERS file if they wish to or
any existing maintainer may open a pull request to the MAINTAINERS file on their
behalf. If the pull request is not initiated by the reviewer, it must be approved
by 2/3 of the current committers or by the reviewer who is being removed. The
voting and discussion period is seven days, after which a committer will verify
the votes, merge the pull request, and apply the changes to the organization.

## Emeritus maintainers

For committers who are stepping down or being removed due to inactivity,
the project would like to memorialize their contributions to the project by
recognizing them as Emeritus maintainers in the EMERITUS.md file. The EMERITUS.md
file will include a brief paragraph summarizing their contribution to the
containerd project and recognize them as permanent Emeritus members of the
community. While Emeritus maintainers are not active in the project, their
expertise is always valued and their LGTM may count towards the required LGTM
count to merge a code change into the project.

If in the future an Emeritus maintainer has the desire or ability to return to
contributing to the project, Emeritus maintainers can submit a pull request
reversing their removal from the MAINTAINERS file and approval only requires
2 LGTMs from current committers to return to full committer status in the
project.

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


## Breaking changes (backward/forward)

A breaking change is a modification to a supported feature of a public service or API that breaks with prior releases (backwards) and in some cases future releases (forwards.. both potential or real).

I. Backwards - If it is necessary to consider a breaking change, effort will be made to:
   a. get input from impacted parties
   b. provide proper notice and workarounds
   c. avoid cherry picking the change to supported releases
   d. restrict breaking changes to the main branch targeted for a next major release boundary

II. Forwards - When drafting a public service/api care should be taken to keep the API free from overly restrictive content checking that would easily break in the future if for example, an additional field is added, in the future, to a passed in data structure. IOW consideration should be made to be future proof as these apis may be hosted by old containerd binaries for many years, even called by newer versions of clients where a user did not move to the latest containerd but did upgrade the client.

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

Yes. Nobody should ever push to main directly. All changes should be
made through a pull request.

## Conflict Resolution

If you have a technical dispute that you feel has reached an impasse with a
subset of the community, any contributor may open an issue, specifically
calling for a resolution vote of the current core committers to resolve the
dispute. A resolution vote must be approved by 2/3 of the current core
committers.
