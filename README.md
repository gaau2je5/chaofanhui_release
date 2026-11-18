# 炒饭商学院

炒饭商学院的桌面应用（macOS、Windows、Linux）的下载页。这里只放发布的版本，不放源码。

## 下载

到 [Releases](https://github.com/gaau2je5/chaofanhui_release/releases/latest) 下载最新版本，按你的系统选一个文件。文件名不带版本号，下面的链接总是最新版本：

| 系统 | 下载 |
|---|---|
| macOS 12 及以上，Apple 芯片 | [`chaofanhui-macos-arm64.zip`](https://github.com/gaau2je5/chaofanhui_release/releases/latest/download/chaofanhui-macos-arm64.zip) |
| Windows 10/11 x64 | [`chaofanhui-windows-amd64.exe`](https://github.com/gaau2je5/chaofanhui_release/releases/latest/download/chaofanhui-windows-amd64.exe) |
| Windows 11 arm64 | [`chaofanhui-windows-arm64.exe`](https://github.com/gaau2je5/chaofanhui_release/releases/latest/download/chaofanhui-windows-arm64.exe)（未实测） |
| Linux x64 | [`chaofanhui-linux-amd64`](https://github.com/gaau2je5/chaofanhui_release/releases/latest/download/chaofanhui-linux-amd64) |
| Linux arm64 | [`chaofanhui-linux-arm64`](https://github.com/gaau2je5/chaofanhui_release/releases/latest/download/chaofanhui-linux-arm64)（未实测） |

Release 里其他的文件（`chaofanhui-X.Y.Z-*.tar.gz`、`.delta`、`update-*.json`）是给应用自动更新用的，不用下载。

实测过的是 macOS（Apple 芯片）、Windows 11 x64 和 Debian 13 KDE x64；arm64 的 Windows 和 Linux 版本能编出来，但没有真机测过。

## 安装

- **macOS**：解压后把「炒饭商学院.app」拖进「应用程序」。应用从 0.5.0 起改名为「炒饭商学院」，以前的「炒饭会课堂.app」可以删掉，登录和下载记录都还在。
- **Windows**：下载的 `chaofanhui-windows-amd64.exe` 就是应用本身，不用解压、不用安装，放在哪个文件夹都行（「下载」也可以），双击运行。需要系统自带的 WebView2（Windows 11 已有）。
- **Linux**：下载的 `chaofanhui-linux-amd64` 就是应用本身。浏览器下载的文件没有可执行权限，先加上再运行，任选一种：
  - 终端里：

    ```sh
    chmod +x chaofanhui-linux-amd64
    ./chaofanhui-linux-amd64
    ```
  - 文件管理器里：右键 → 属性 → 权限，勾上「可执行」（KDE 的 Dolphin 是「允许作为程序执行」），再双击。

  需要 WebKitGTK 4.1，Debian/Ubuntu 上是 `sudo apt install libwebkit2gtk-4.1-0`；播放视频还需要 GStreamer 的 good、bad、libav 插件。选装 `libayatana-appindicator3-1`（Debian/Ubuntu 上 `sudo apt install libayatana-appindicator3-1`）：不装就没有托盘图标。

## 第一次打开

- **macOS**：应用没有经过 Apple 公证（只有 ad-hoc 签名），第一次打开会被系统拦下。任选一种方式放行：
  - 打开一次被拦后，到「系统设置 → 隐私与安全性」，点「仍要打开」。
  - 或者在终端运行：

    ```sh
    xattr -dr com.apple.quarantine "/Applications/炒饭商学院.app"
    ```
- **Windows**：程序没有签名，SmartScreen 会拦下，点「更多信息」→「仍要运行」。

## 更新

从 0.5.0 起应用能自己更新：有新版本时会提示（设置里可以改成自动更新或不自动检查），确认后下载、校验签名、替换自己，重启就是新版本。

- 应用要放在你自己能写的位置：macOS 的「应用程序」或 `~/Applications`；Windows 和 Linux 就是你放程序的那个文件夹。
- Windows 和 Linux 更新后文件名不变，还是你运行的那个文件。Windows 上更新到重启之间，旁边会多一个 `.chaofanhui-windows-amd64.exe.old-数字` 的旧文件（运行中的程序删不掉），重启后自动删掉。
- 如果程序所在的文件夹里正好有一个叫 `炒饭商学院.exe`（Windows）或 `chaofanhui`、`chaofanhui.desktop`、`chaofanhui.png`（Linux）的文件，应用为了不覆盖它就不自动更新，设置里会写明。把程序单独放进一个文件夹就好。

0.3.0–0.3.2 不会自动更新，从这里手动下载一次新版本就行。

## 校验

每个 Release 的 SHA-256 见附件 `SHA256SUMS.txt`。
