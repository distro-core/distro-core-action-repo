# Github Action: DISTRO Core Repo Init/Sync

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

Copyright (c) 2025 brainhoard.com

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](./LICENSE).

Editorial discretion is asserted on specific inclusion of layers that
may referenced. All upstream packages and their source code come with
their respective licenses. Individual packages license terms are to be
respected.

## Usage:

~~~ yaml
name: Tests

on:
  workflow_dispatch:

jobs:
  test:
    steps:
    # place in caller workflow when repo is expected to override details
    # of a project based on branch or revision differences.
    # - id: repo-local-manifest
    #   shell: bash
    #   run: |
    #     : repo-local-manifests
    #     install -d .repo/local_manifests
    #     cat <<EOF >.repo/local_manifests/local_manifest.xml
    #     <?xml version="1.0" encoding="UTF-8"?>
    #     <manifest>
    #     <!-- <extend-project name="meta-tegra" revision="scarthgap-l4t-r35.x" upstream="scarthgap-l4t-r35.x" dest-branch="scarthgap-l4t-r35.x"/> -->
    #     </manifest>
    #     EOF
    - uses: distro-core/distro-core-action-repo@main
      with:
        MANIFEST_URL: https://github.com/distro-core/distro-manifest.git
        MANIFEST_NAME: distro-head-scarthgap.xml
        MANIFEST_REF: main
~~~
