# code-server for TOS 7 (Docker)

在浏览器中使用 VS Code 的远程开发环境。打开 NAS 上的目录进行编辑，使用终端与扩展，工作区与配置保存在应用数据目录。

Run VS Code in the browser. Open folders on the NAS, use the terminal and extensions, with workspace and settings kept in the application data directory.

## Package

- Application ID: `coder-code-server`
- Type: Docker (TOS 7)
- Architecture: `x86_64`, `aarch64`
- Upstream image: see `docker-compose.yml` in the downloaded asset
- Web UI port: declared in `x-app-meta`

## Source

The `src/` directory contains the files the package is built from:

- `src/config.x86_64.ini` / `src/config.aarch64.ini` — `config.ini` per architecture
- `src/docker-compose.yml` — compose template; `@@...@@` placeholders are replaced at build time
- `src/coder-code-server.lang` — 14 language sections
- `src/coder-code-server.svg` — application icon

Build toolchain: https://github.com/Irvingfei/tos-docker-apps

## Install

1. In the TOS App Center, add this repository's application and submit the matching `coder-code-server_<arch>.tar.gz` asset from the latest Release.
2. Data is stored under `/Volume<N>/DockerAppData/coder-code-server/` through the compose bind mounts.

## Notes

首次启动会自动生成随机登录密码，保存在容器内 /home/coder/.config/code-server/config.yaml；可在容器终端查看，登录后也可在设置中修改。

This repository packages the upstream open-source application for TerraMaster TOS 7.
It is not affiliated with or endorsed by the upstream project. Application names and
trademarks belong to their respective owners. All images are pulled from Docker Hub.
