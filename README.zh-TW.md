# SysTools

[English](README.md) | **繁體中文** | [日本語](README.ja.md)

SysTools 是全畫面的終端機系統管理主控台，支援 Linux（systemd）與 macOS。服務、行程、CPU、記憶體、磁碟、網路、紀錄、排程、登入連線、檔案管理員、腳本逐步執行與設定檔編輯，集中在同一個鍵盤操作介面。

這個 repository 只放發布的執行檔，不公開原始碼。

產品網站：[systools.spex.com.tw](https://systools.spex.com.tw)

## 下載

| 平台 | 檔案 |
| --- | --- |
| Linux，Intel／AMD 64-bit（systemd） | `systools-linux-amd64.tar.gz` |
| Linux，ARM64（systemd） | `systools-linux-arm64.tar.gz` |
| macOS，Apple Silicon | `systools-macos-arm64.tar.gz` |

請到[最新版本](https://github.com/walisayu/systools/releases/latest)下載。Linux 版在 Rocky Linux 8（glibc 2.28）環境建置，可在 RHEL、Rocky Linux、AlmaLinux 8 以上，以及其他 glibc 2.28 以上的發行版執行；已在 Rocky Linux 8、Debian 12、Ubuntu 24.04 上實測。

## 安裝

Linux（ARM64 主機把 `amd64` 換成 `arm64`）：

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

用 `curl` 下載的檔案可以直接執行。如果是用瀏覽器下載壓縮檔，macOS 會標記為隔離，解壓縮後請執行一次 `xattr -d com.apple.quarantine systools`。

## 第一次使用

```bash
systools --check     # 檢查這台主機能不能收集資料，不會進入互動畫面
sudo systools        # 進入互動介面
```

監控功能用一般使用者即可。Linux 上要啟動、停止、重新啟動服務需要 `sudo`，macOS 上管理系統層級的 LaunchDaemons 也一樣。

## 使用條款

Copyright © SPEX Technology Co., Ltd. 保留所有權利。軟體以現狀提供，不附任何形式的保證。授權相關問題請洽 sales@spex.com.tw。
