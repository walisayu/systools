# SysTools

**English** | [繁體中文](README.zh-TW.md)

SysTools is a full-screen terminal console for system administration on Linux (systemd) and macOS. Services, processes, CPU, memory, disks, network, logs, schedules, login sessions, a file manager, a step-by-step script runner, and config file editing share one keyboard-driven interface.

This repository only hosts the release builds. The source code is not published.

Product page: https://systools.spex.com.tw

## Download

| Platform | File |
| --- | --- |
| Linux, Intel / AMD 64-bit (systemd) | `systools-linux-amd64.tar.gz` |
| Linux, ARM64 (systemd) | `systools-linux-arm64.tar.gz` |
| macOS, Apple Silicon | `systools-macos-arm64.tar.gz` |

Get them from the [latest release](https://github.com/walisayu/systools/releases/latest). The Linux builds are built on Debian 12 and tested on Ubuntu 24.04.

## Install

Linux (use `arm64` instead of `amd64` on ARM64 hosts):

```bash
curl -LO https://github.com/walisayu/systools/releases/latest/download/systools-linux-amd64.tar.gz
curl -LO https://github.com/walisayu/systools/releases/latest/download/SHA256SUMS.txt
sha256sum --ignore-missing -c SHA256SUMS.txt
tar -xzf systools-linux-amd64.tar.gz
sudo install -m 0755 systools /usr/local/bin/systools
```

macOS (Apple Silicon):

```bash
curl -LO https://github.com/walisayu/systools/releases/latest/download/systools-macos-arm64.tar.gz
curl -LO https://github.com/walisayu/systools/releases/latest/download/SHA256SUMS.txt
grep macos SHA256SUMS.txt | shasum -a 256 -c
tar -xzf systools-macos-arm64.tar.gz
sudo install -m 0755 systools /usr/local/bin/systools
```

Files downloaded with `curl` can be run directly. If you download the archive in a browser, macOS marks it as quarantined; run `xattr -d com.apple.quarantine systools` once after extracting.

## First run

```bash
systools --check     # checks that this host can collect data; does not open the interface
sudo systools        # starts the interface
```

Monitoring works as a regular user. Starting, stopping, and restarting services needs `sudo` on Linux, and for system-level LaunchDaemons on macOS.

## Terms

Copyright © SPEX Technology Co., Ltd. All rights reserved. The software is provided as is, without warranty of any kind. For licensing questions, contact sales@spex.com.tw.
