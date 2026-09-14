## gitlab-runner-helper 的基础镜像

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

## 概述

本项目为 **loong64**（龙芯架构）构建 GitLab Runner 的基础镜像。它是 [kubernetes-loong64](https://github.com/kubernetes-loong64) 项目的子模块。

上游 base-images 项目（[gitlab-org/ci-cd/runner-tools/base-images](https://gitlab.com/gitlab-org/ci-cd/runner-tools/base-images)）面向 `linux/amd64`。本仓库通过补丁将上游适配为 `linux/loong64` 镜像，使用 **Debian 14**（来自 `lcr.loongnix.cn`）替代 Ubuntu 作为基础镜像。

[![kubernetesloong64/runner-tools-base-images-loong64](https://img.shields.io/docker/v/kubernetesloong64/runner-tools-base-images-loong64?logo=docker&label=kubernetesloong64%2Frunner-tools-base-images-loong64)](https://hub.docker.com/r/kubernetesloong64/runner-tools-base-images-loong64/tags)

## 分支

| 分支                | 描述                                      |
|-------------------|-----------------------------------------|
| `main`            | 项目文档、许可证和公共配置                           |
| `loong64-v0.0.50` | 基于上游 base-images v0.0.50 的 loong64 适配构建 |

新的 loong64 发布分支遵循命名约定 `loong64-<上游版本号>`。

## 验证发布

- 发布文件使用 GPG 签名。
- 从 [keys.openpgp.org](https://keys.openpgp.org) 下载公钥。
- 指纹：[FCF8724722CCBF9F51B1FBE376532BE7E3013105](https://keys.openpgp.org/debug?q=FCF8724722CCBF9F51B1FBE376532BE7E3013105)
- [手动下载](https://keys.openpgp.org/vks/v1/by-fingerprint/FCF8724722CCBF9F51B1FBE376532BE7E3013105)

```shell
gpg --keyserver keys.openpgp.org --recv-keys FCF8724722CCBF9F51B1FBE376532BE7E3013105
echo "FCF8724722CCBF9F51B1FBE376532BE7E3013105:6:" | gpg --import-ownertrust
```

或者，手动下载公钥文件后导入：

```shell
gpg --import /tmp/xxx
```

## 许可证

[Apache License 2.0](LICENSE)
