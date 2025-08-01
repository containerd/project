# Contributing

Contributions should be made via pull requests. Pull requests will be reviewed
by one or more maintainers and merged when acceptable.

The goal of the containerd project is to enable developers to build container
platforms on top of the APIs that the containerd projects expose.
The main entry point for a containerd consumer is the Go API. `ctr` is a
development tool to quickly test features of containerd and is unsupported in
a production setting. The project has zero plans of supporting `ctr` in the future.

When developing features inside the containerd codebase, changes should be focused
towards building APIs to develop higher level functionality and not about adding a
specific feature into the core codebase.
Some features may benefit the container ecosystem, however, they may not be
appropriate for a first class feature in containerd.

## Successful Changes

We ask that before contributing, please make the effort to coordinate with the
maintainers of the project before submitting large or high impact PRs. This
will prevent you from doing extra work that may or may not be merged.

PRs that are just submitted without any prior communication will likely be
summarily closed.

While pull requests are the methodology for submitting changes to code, changes
are much more likely to be accepted if they are accompanied by additional
engineering work. While we don't define this explicitly, most of these goals
are accomplished through communication of the design goals and subsequent
solutions. Often times, it helps to first state the problem before presenting
solutions.

Typically, the best methods of accomplishing this are to submit an issue,
stating the problem. This issue can include a problem statement and a
checklist with requirements. If solutions are proposed, alternatives should be
listed and eliminated. Even if the criteria for elimination of a solution is
frivolous, say so.

Larger changes typically work best with design documents, similar to those found
in `design/`. These are focused on providing context to the design at the time
the feature was conceived and can inform future documentation contributions.

Make sure that new tests are added for bugs in order to catch regressions and tests
with new features to exercise the new functionality that is added.

## Commit Messages

There are times for one line commit messages and this is not one of them.
Commit messages should follow best practices, including explaining the context
of the problem and how it was solved, including in caveats or follow up changes
required. They should tell the story of the change and provide readers
understanding of what led to it.

If you're lost about what this even means, please see [How to Write a Git
Commit Message](http://chris.beams.io/posts/git-commit/) for a start.

In practice, the best approach to maintaining a nice commit message is to
leverage a `git add -p` and `git commit --amend` to formulate a solid
changeset. This allows one to piece together a change, as information becomes
available.

If you squash a series of commits, don't just submit that. Re-write the commit
message, as if the series of commits was a single stroke of brilliance.

That said, there is no requirement to have a single commit for a PR, as long as
each commit tells the story. For example, if there is a feature that requires a
package, it might make sense to have the package in a separate commit then have
a subsequent commit that uses it.

If there are multiple authors who worked together on a PR that needs to be squashed,
please use `Co-authored-by` to indicate each person who contributed to the PR. This
enables automated tools
and [Github](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/creating-a-commit-with-multiple-authors)
to highlight everyone's role in the PR.

Remember, you're telling part of the story with the commit message. Don't make
your chapter weird.

## Applying License Header to New Files

If you submit a contribution that adds a new file, please add the license
header. You can do so manually or use the `ltag` tool. The `ltag` templates
for filetypes are in the `containerd/project-checks` repository but the files you want
to tag are most likely in the main containerd project or any of the possible
subprojects. You can pass the path to the project repo root to `ltag` but you
should run `ltag` in the directory where you have new files.


```console
$ go get github.com/kunalkushwaha/ltag
$ ltag -t {containerd/project-checks rootdir}/script/validate/template
```

The above will add the appropriate license header to Go language source files,
 Makefiles, Dockerfiles, and shell scripts. New templates will need to be added
 if other kinds of files are added. Please consult the
documentation at https://github.com/kunalkushwaha/ltag

## Sign your work

The sign-off is a simple line at the end of the explanation for the patch. Your
signature certifies that you wrote the patch or otherwise have the right to pass
it on as an open-source patch. The rules are pretty simple: if you can certify
the below (from [developercertificate.org](http://developercertificate.org/)):

```
Developer Certificate of Origin
Version 1.1

Copyright (C) 2004, 2006 The Linux Foundation and its contributors.
660 York Street, Suite 102,
San Francisco, CA 94110 USA

Everyone is permitted to copy and distribute verbatim copies of this
license document, but changing it is not allowed.

Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

Then you just add a line to every git commit message:

    Signed-off-by: Joe Smith <joe.smith@email.com>

Use your real name (sorry, no pseudonyms or anonymous contributions.)

If you set your `user.name` and `user.email` git configs, you can sign your
commit automatically with `git commit -s`.
