# SysTools

[English](README.md) | [繁體中文](README.zh-TW.md) | **日本語**

SysTools は、Linux（systemd）と macOS 向けのフルスクリーンのターミナル系システム管理コンソールです。サービス、プロセス、CPU、メモリ、ディスク、ネットワーク、ログ、スケジュール、ログインセッション、ファイルマネージャー、スクリプトのステップ実行、設定ファイルの編集を、ひとつのキーボード操作インターフェースにまとめています。

このリポジトリにはリリースビルドのみを置いています。ソースコードは公開していません。

製品サイト：[systools.spex.com.tw](https://systools.spex.com.tw)

## ダウンロード

| プラットフォーム | ファイル |
| --- | --- |
| Linux、Intel / AMD 64-bit（systemd） | `systools-linux-amd64.tar.gz` |
| Linux、ARM64（systemd） | `systools-linux-arm64.tar.gz` |
| macOS、Apple Silicon | `systools-macos-arm64.tar.gz` |

[最新リリース](https://github.com/walisayu/systools/releases/latest)からダウンロードしてください。Linux 版は Rocky Linux 8（glibc 2.28）でビルドしているため、RHEL・Rocky Linux・AlmaLinux 8 以降、およびその他の glibc 2.28 以降のディストリビューションで動作します。Rocky Linux 8、Debian 12、Ubuntu 24.04 で動作を確認しています。

## インストール

Linux（ARM64 のホストでは `amd64` を `arm64` に置き換えてください）：

```bash
curl -LO https://github.com/walisayu/systools/releases/latest/download/systools-linux-amd64.tar.gz
curl -LO https://github.com/walisayu/systools/releases/latest/download/SHA256SUMS.txt
sha256sum --ignore-missing -c SHA256SUMS.txt
tar -xzf systools-linux-amd64.tar.gz
sudo install -m 0755 systools /usr/local/bin/systools
```

macOS（Apple Silicon）：

```bash
curl -LO https://github.com/walisayu/systools/releases/latest/download/systools-macos-arm64.tar.gz
curl -LO https://github.com/walisayu/systools/releases/latest/download/SHA256SUMS.txt
grep macos SHA256SUMS.txt | shasum -a 256 -c
tar -xzf systools-macos-arm64.tar.gz
sudo install -m 0755 systools /usr/local/bin/systools
```

`curl` でダウンロードしたファイルはそのまま実行できます。ブラウザでアーカイブをダウンロードした場合は macOS が隔離フラグを付けるため、展開後に一度だけ `xattr -d com.apple.quarantine systools` を実行してください。

## 初回起動

```bash
systools --check     # このホストでデータを収集できるか確認します。対話画面は開きません
sudo systools        # 対話画面を起動します
```

監視は一般ユーザーで動作します。サービスの起動・停止・再起動には、Linux では `sudo` が必要です。macOS でもシステムレベルの LaunchDaemons を管理する場合は `sudo` が必要です。

## 利用条件

Copyright © SPEX Technology Co., Ltd. All rights reserved. 本ソフトウェアは現状のまま提供され、いかなる保証もありません。ライセンスに関するお問い合わせは sales@spex.com.tw までご連絡ください。
