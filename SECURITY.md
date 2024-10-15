# Security Policy

## Reporting a Vulnerability

To report a containerd vulnerability:

* Navigate to the security tab on the repository
![Github Security Tab](./img/Security-Tab.png)

* Click on `Advisories`
![Github Advisories tab](./img/Advisories.png)

* Click on `Report a vulnerability`
![Report a vulnerability](./img/Report-A-Vulnerability.png)

The reporter(s) can expect a response within 24 hours acknowledging
the issue was received. If a response is not received within 24 hours, please
reach out to any committer directly to confirm receipt of the issue.

## Review Process

Once a committer has confirmed the relevance of the report, a draft security
advisory will be created on Github. The draft advisory will be used to discuss
the issue with committers, the reporter(s), and containerd's security advisors.
If the reporter(s) wishes to participate in this discussion, then provide
reporter Github username(s) to be invited to the discussion. If the reporter(s)
does not wish to participate directly in the discussion, then the reporter(s)
can request to be updated regularly via email.

If the vulnerability is accepted, a timeline for developing a patch, public
disclosure, and patch release will be determined. If there is an embargo period
on public disclosure before the patch release, an announcment will be sent to
the security announce mailing list(`containerd-security-announce@lists.cncf.io`)
announcing the scope of the vulnerability, the date of availability of the
patch release, and the date of public disclosure. The reporter(s) are expected
to participate in the discussion of the timeline and abide by agreed upon dates
for public disclosure.

## Supported Versions

See the [containerd releases page](https://github.com/containerd/containerd/blob/master/RELEASES.md#support-horizon)
for information on supported versions of containerd. Any `Extended` or `Active`
release branch may receive security updates. For any security issues discovered
on older versions, non-core packages, or dependencies, please inform committers
using the same security mailing list as for reporting vulnerabilities.

## Joining the security announce mailing list

Any organization or individual who directly uses containerd and non-core
packages in production or in a security critical application is eligible to join
the security announce mailing list. Indirect users who use containerd through a
vendor are not expected to join, but should request their vendor join. To join
the mailing list, the individual or organization must be sponsored by either a
containerd committer or security advisor as well as have a record of properly
handling non-public security information.
Sponsorship should not be requested via public channels since membership of the
security announce list is not public.
