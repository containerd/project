# README

## How to use it to help create a release

### Step 1

Use `go build` to compile project.

### Step 2

Create a release file, and this is a template

```toml
# commit to be tagged for new release
commit = "HEAD"

project_name = "Dragonfly"
github_repo = "dragonflyoss/Dragonfly"
match_deps = "^github.com/(dragonflyoss/[a-zA-Z0-9-]+)$"

# previous release
previous = "v0.3.0"

# whether this is a pre-release version
pre_release = false

preface = """\
This is a text preface text.
"""

supernode_image = "https://hub.docker.com/r/dragonflyoss/supernode/tags"
df_client_image = "https://hub.docker.com/r/dragonflyoss/dfclient/tags"

breaking_changes = """\
* This is a break item 1.
* This is a break item 2.
"""
```

### Step 3

Use this command to generate a release note.

```shell
VERSION="v0.4.0"
release-tool -n -d -t $VERSION release-template.toml > $VERSION.note
```
