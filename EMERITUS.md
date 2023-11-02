# containerd Emeritus Maintainers

## John Howard [@lowenna](https://github.com/lowenna)

John's tremendous efforts to get containers working on Windows lead to cross-platform images
as they are known today. Due to his work, containerd has first class support for Windows and
contributed to it being the most cross-platform capable container runtime.

## Kenfe-Mickaël Laventure [@mlaventure](https://github.com/mlaventure)

One of the first contributors to containerd, Mickaël led the effort to get the first
versions of containerd used as the runtime for dockerd. He has made a significant impact on the
runtime codebase from the API to the OCI runtime.

## Abhinandan Prativadi [@abhi](https://github.com/abhi)

A significant contributor to the CRI plugin and container networking, Abhi helped make
containerd a reliable and complete container runtime for Kubernetes.

## Lantao Liu [@Random-Liu](https://github.com/Random-Liu)

Lantao Liu was one of the initial authors of the containerd CRI plugin.  Lantao
worked across the Kubelet, Kubernetes project infrastructure, CRI, and
containerd to enable containerd to be one of the first CRI-enabled runtimes for
Kubernetes.  containerd is now the default container runtime for several
Kubernetes providers, which would not have been possible without Lantao's
dedicated work.  While Lantao is no longer involved in the day-to-day
maintenance of the CRI plugin or containerd in general, he remains involved in
the larger Kubernetes community.

## Dawn Chen [@dchen1107](https://github.com/dchen1107)

Dawn Chen was the initiator of CRI for Kubernetes, and an important partner in
enabling the containerd CRI plugin to happen.  Dawn coordinated the needs of
Kubernetes SIG-Node with containerd.  containerd is now well-supported and a
critical part of Kubernetes validation, which would not have been possible
without Dawn’s advocacy.  While Dawn is no longer involved in the day-to-day
maintenance of the CRI plugin or containerd in general, she continues to serve
as a Technical Lead for SIG-Node and an advocate for containerd in the
Kubernetes community.

## Yu-Ju Hong [@yujuhong](https://github.com/yujuhong)

Yu-Ju Hong proposed the first version of CRI and was a key part of early
implementation of the containerd CRI plugin.  Her work enabled Kubernetes to
invoke runtimes via CRI, allowed the Kubernetes CI environment to test CRI
integrations like containerd, and provided a standard set of tools and test
suite for container runtimes.  While Yu-Ju is not currently involved in
containerd, she remains involved in the larger Kubernetes community.

## Stephen Day [@stevvooe](https://github.com/stevvooe)

Both the author of the initial distribution specification and architect behind
many of the containerd 1.0 designs, Stephen Day has had a tremendous impact on
the container ecosystem. The containerd project has greatly benefited from
Stephen’s bold and innovative ideas along with his large impact on the
containerd codebase. We can both thank and `git blame` Stephen for many parts of
containerd.
