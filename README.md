## gitlab-runner-helper base images

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

## Overview

This project builds base images for GitLab Runner on the **loong64** (LoongArch) architecture. It is a submodule of the [kubernetes-loong64](https://github.com/kubernetes-loong64) project.

The upstream base-images project ([gitlab-org/ci-cd/runner-tools/base-images](https://gitlab.com/gitlab-org/ci-cd/runner-tools/base-images)) targets `linux/amd64`. This repository patches the upstream to produce `linux/loong64` images, using **Debian 14** (from `lcr.loongnix.cn`) as the base instead of Ubuntu.

[![kubernetesloong64/runner-tools-base-images-loong64](https://img.shields.io/docker/v/kubernetesloong64/runner-tools-base-images-loong64?logo=docker&label=kubernetesloong64%2Frunner-tools-base-images-loong64)](https://hub.docker.com/r/kubernetesloong64/runner-tools-base-images-loong64/tags)

## Branches

| Branch            | Description                                                         |
|-------------------|---------------------------------------------------------------------|
| `main`            | Project documentation, license, and shared configuration            |
| `loong64-v0.0.50` | Patched build for upstream base-images v0.0.50 with loong64 support |

New loong64 release branches follow the naming convention `loong64-<upstream-version>`.


## Verifying releases

- Releases are signed with GPG.
- Download the public key from [keys.openpgp.org](https://keys.openpgp.org).
- Fingerprint: [FCF8724722CCBF9F51B1FBE376532BE7E3013105](https://keys.openpgp.org/debug?q=FCF8724722CCBF9F51B1FBE376532BE7E3013105)
- [Manual download](https://keys.openpgp.org/vks/v1/by-fingerprint/FCF8724722CCBF9F51B1FBE376532BE7E3013105)

```shell
gpg --keyserver keys.openpgp.org --recv-keys FCF8724722CCBF9F51B1FBE376532BE7E3013105
echo "FCF8724722CCBF9F51B1FBE376532BE7E3013105:6:" | gpg --import-ownertrust
```

Or download the key file manually and import it:

```shell
gpg --import /tmp/xxx
```

## License

[Apache License 2.0](LICENSE)
