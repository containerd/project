# Collaboration with Kubernetes SIG-Node

containerd is a popular container runtime used with
[Kubernetes](https://kubernetes.io).  containerd implements the Kubernetes
Container Runtime Interface (CRI) and is expected to participate in the
development and implementation of CRI.

Changes to Kubernetes (including CRI) are primarily driven through the
[Kubernetes Enhancement Proposal (KEP) process](https://github.com/kubernetes/enhancements).
KEPs are proposed to individual Special Interest Groups (SIGs) within the
Kubernetes project, which help to refine, clarify, and decide the content of an
individual KEP as well as drive its implementation.  CRI-related KEPs are
primarily handled through SIG-Node.  SIG-Node has
[adopted a policy](https://www.kubernetes.dev/docs/code/cri-api-dev-policies/)
which requires KEPs to reach maturity in both containerd and CRI-O before
advancing through graduation stages.

This document describes the process that the containerd project uses to
collaborate with SIG-Node on any KEP or other CRI-related change.

## Goals

* Provide visibility of SIG-Node integration work for containerd (including
  KEPs) for:
  * containerd maintainers and community members who are not directly involved
    in SIG-Node
  * SIG-Node participants who are not involved in the containerd community
* Ensure containerd maintainers and communtiy members have adequate
  opportunities to participate in design without requiring full context on
  every SIG-Node KEP or who are not familiar with the KEP process
* Ensure contributors understand the status of their proposed contributions
* Spread the KEP tracking and review load among interested maintainers, and
  enable at least two interested containerd maintainers per KEP or
  Kubernetes-related work item in order to facilitate knowledge sharing

## Non-goals

* Change the development or release process of containerd.  See the
  [contribution guidelines](CONTRIBUTING.md) and
  [versioning and release](https://containerd.io/releases) page.
* Guarantee KEP delivery, outside of providing feedback during KEP design,
  guiding contributors through processes, and reviews.

## Roles

* SIG-Node member liaison - a containerd maintainer responsible for
  facilitating communication between SIG-Node and the containerd project
  regarding KEP status, targeted containerd releases, and any other integration
  work or pain points.
* KEP shepherd - for each KEP, at least one (preferably two) containerd
  maintainer(s) responsible for helping a KEP move through the implementation
  and release process in containerd.

## Metadata

* Per-KEP issue in the
  [containerd/containerd](https://github.com/containerd/containerd) repository
  for tracking KEPs that require CRI changes in the container
  runtime or one of our other containerd subprojects.  (This includes
  relatively minor changes, such as a runc update or checking containerd config
  to align defaults with feature gate GAs.)
* Labels within the containerd/containerd repository corresponding to
  Kubernetes minor releases, applied to KEP tracking issues and PRs
* Recording the assigned shepherd(s) on the KEP tracking issue

## Process

For a KEP to be reviewed and implemented in containerd:

### Issue management

* An issue should be created in the
  [containerd/containerd repository](https://github.com/containerd/containerd)
  tracking the individual KEP as soon as possible
  * containerd KEP tracking issues may be opened by one of the KEP owners,
    an interested maintainer, or by a group within SIG-Node that is managing
    the KEP process
  * This includes all KEPs for SIG-Node, whether they are in Draft or Approved
    status.  The same issue should continue to track the KEP through each
    stage, alpha(s), beta(s), and GA
  * The new issue title should include both the KEP number and a short title or
    description of the goal of the KEP
* containerd maintainers will triage new KEP tracking issues as needed
* KEP tracking issues should be added to a label for the Kubernetes release
  cycle within the containerd/containerd repository during triage

### SIG-Node Liaison

At least one containerd maintainer will be responsible to liaise with SIG-Node
for each Kubernetes release cycle.  The liaison role involves:

* Tracking the status of each KEP both in containerd and the larger context in
  Kubernetes (including the status of the KEP in kubelet and/or other
  involved/dependent SIGs / projects).
* Tracking the status of the other types of Node Integration pain points
  critical to the upcoming kubernetes releases (likely via issue)
* Communicating which containerd release(s) will include a given KEP (usually
  the next minor release in our
  [6-month release cadence](https://containerd.io/releases/#release-cadence))
  and whether there are implications to prior containerd releases as KEPs are
  promoted
* Ensuring other types of SIG-Node integration pain points have at least one
  containerd maintainer assigned. These include urgent Kubernetes PRs that
  require containerd support and standard issues that don’t require a KEP, long
  running infra tasks, major critest/crictl interop up on
  kubernetes-sigs/critools, etc.
* Being a
  [Kubernetes org member](https://github.com/kubernetes/community/blob/master/community-membership.md#member)
  and
  [SIG-Node member](https://github.com/kubernetes/community/blob/master/sig-node/sig-node-contributor-ladder.md)
  (prerequisite for volunteering)
* Being available in the `#sig-node` channel of the [Kubernetes slack](https://slack.kubernetes.io)

### KEP shepherd

At least one containerd maintainer will be assigned (as part of KEP triage) to
shepherd each active KEP planned for integration with containerd.  An active
KEP is one which has already been implemented in an existing Kubernetes release
or is being considered for an upcoming Kubernetes release.  The shepherd role
involves:

* Engaging as early as possible in the KEP discussion (via the primary KEP
  issue, `#sig-node` Slack channel, and SIG-Node weekly calls) and design to
  represent the containerd maintainer perspective in terms of
  architecture/layering (i.e., should the new functionality reside in the
  runtime, Kubelet, or some other component) and priority so that
  implementation can be scheduled into an upcoming release.
* Ensuring maintainers have consensus on how the KEP should be implemented in
  containerd and communicating to the KEP owner and our liaison if consensus on
  implementation details and/or timing cannot be reached in time for the next
  minor release.
* Ensuring the implementation design discussion happens in the open and
  transparently; allowing proposals from the KEP owner, contributors, and
  maintainers.
* Coordinating contributors to implement the KEP
* Coordinating the review and merge of containerd side KEP-related PRs
  coinciding with required k/k CRI, kubelet, and other project dependencies
  * Shepherds should provide initial review of the containerd PRs
  * Shepherds should ensure that documentation for any new CRI API clearly
    articulates any guarantees that containerd must provide and any API
    behaviors that are not clear from the API declaration
* Assist the liason(s) with reviews of the other KEP dependent PRs, such as CRI
  API changes, Kubelet changes, etc.
* Communicating the status of the KEP clearly on the tracking issue which will
  be cross linked to the KEP issue document, PRs, and other SIG-Node tracking
  documents.
* The shepherd role is not necessarily responsible for designing or
  implementing the KEP themselves