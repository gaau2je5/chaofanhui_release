# 炒饭会课堂

炒饭会课堂的桌面应用（macOS、Windows、Linux）的下载页。这里只放发布的版本，不放源码。

## 下载

到 [Releases](https://github.com/gaau2je5/chaofanhui_release/releases/latest) 下载最新版本，按你的系统选一个文件（`X.Y.Z` 是版本号）：

| 系统 | 下载 |
|---|---|
| macOS 12 及以上，Apple 芯片 | `chaofanhui-X.Y.Z-macos-arm64.zip` |
| Windows 10/11 x64 | `chaofanhui-X.Y.Z-windows-amd64.zip` |
| Windows 11 arm64 | `chaofanhui-X.Y.Z-windows-arm64.zip`（未实测） |
| Linux x64 | `chaofanhui-X.Y.Z-linux-amd64.tar.gz` |
| Linux arm64 | `chaofanhui-X.Y.Z-linux-arm64.tar.gz`（未实测） |

Release 里其他的文件（`chaofanhui-X.Y.Z-darwin-arm64.tar.gz`、`chaofanhui-X.Y.Z-windows-*.tar.gz`、`.delta`、`update-*.json`）是给应用自动更新用的，不用下载。

实测过的是 macOS（Apple 芯片）、Windows 11 x64 和 Debian 13 KDE x64；arm64 的 Windows 和 Linux 版本能编出来，但没有真机测过。

## 安装

- **macOS**：解压后把「炒饭会课堂.app」拖进「应用程序」，替换旧版本。
- **Windows**：把 zip 解压到一个你选的文件夹（比如「文档\炒饭会课堂」），运行里面的 `炒饭会课堂.exe`；`icon.png` 留在它旁边。以后更新会在这个文件夹里原地替换，不要给 exe 改名。需要系统自带的 WebView2（Windows 11 已有）。0.3.x 下载的是单个 exe，换成 zip 解压出来的这个就行。
- **Linux**：解压后运行 `chaofanhui`。需要 WebKitGTK 4.1，Debian/Ubuntu 上是 `sudo apt install libwebkit2gtk-4.1-0`；播放视频还需要 GStreamer 的 good、bad、libav 插件。选装 `libayatana-appindicator3-1`（Debian/Ubuntu 上 `sudo apt install libayatana-appindicator3-1`）：不装就没有托盘图标。

## 第一次打开

- **macOS**：应用没有经过 Apple 公证（只有 ad-hoc 签名），第一次打开会被系统拦下。任选一种方式放行：
  - 打开一次被拦后，到「系统设置 → 隐私与安全性」，点「仍要打开」。
  - 或者在终端运行：

    ```sh
    xattr -dr com.apple.quarantine "/Applications/炒饭会课堂.app"
    ```
- **Windows**：`炒饭会课堂.exe` 没有签名，SmartScreen 会拦下，点「更多信息」→「仍要运行」。

## 更新

带自动更新的版本发布后，应用能自己更新：有新版本时会提示，确认后下载、校验签名、替换自己，重启就是新版本。应用要放在你自己能写的位置（macOS 的「应用程序」或 `~/Applications`，Windows 和 Linux 是解压出来的那个文件夹）。自动更新会在之后的一个版本里加上，加上之前每个版本都从这里手动下载。

0.3.0–0.3.2 不会自动更新，从这里手动下载一次新版本就行。

## 校验

每个 Release 的 SHA-256 见附件 `SHA256SUMS.txt`。
