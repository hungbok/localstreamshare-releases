# LocalStreamShare

<p align="center"><img src="https://raw.githubusercontent.com/hungbok/localstreamshare-releases/main/icon.png" width="112" alt="LocalStreamShare"></p>

[下载 Windows 版](https://github.com/hungbok/localstreamshare-releases/releases/latest) · [English](README.md) · [한국어](README.ko.md) · [日本語](README.ja.md) · [繁體中文](README.zh-TW.md)

以超低延迟将**您选择的画面和声音**串流到同一 Wi‑Fi/局域网内的手机、电脑和电视。观看端只需用浏览器打开地址。开发者：**HungBok**

## 主要功能

- **只在您自己的网络内运行。** 视频从电脑直接发送到观看设备 (WebRTC)。无需账号，不经过外部服务器，没有时间限制。
- **画面来源**：显示器、单个窗口、采集卡/摄像头 (不经过电脑屏幕直接串流)、视频文件、手机或其他电脑的屏幕
- **音频来源**：输出设备、仅特定应用 (或排除特定应用)、麦克风、采集卡声音。可分别设置音量并混合。
- 面向游戏的**超低延迟预设**：硬件 H.264 · 60fps · 1080p，观看端缓冲最小化
- **GPU 画质增强**：超分辨率 (FSR 1.0、Anime4K)、抗锯齿、降噪、帧生成 (运动插帧)、色彩校正
- **以手机作为来源**：Android 通过无线调试获取画面、声音并可操控 (无需安装应用)；任何设备都可用浏览器；iPhone 可用 RTMP 直播应用
- 预览全屏、性能面板 (F3)、访问 PIN、连接用二维码
- 支持韩语、英语、日语、简体中文和繁体中文。观看页面按打开设备的语言显示。

## 安装

1. 从 [Releases](https://github.com/hungbok/localstreamshare-releases/releases/latest) 下载 `LocalStreamShare-Setup-x.y.z.exe` 并运行。
2. 选择语言、安装位置和快捷方式。程序为所有用户安装，会请求一次管理员权限。
3. 安装程序没有代码签名，Windows SmartScreen 可能会发出警告。请确认文件来自本页面，然后选择**更多信息 → 仍要运行**。
   - 如果开启了**智能应用控制** (部分新的 Windows 11 电脑)，Windows 会直接阻止所有未签名的程序。可在 **Windows 安全中心 → 应用和浏览器控制** 中查看状态。
4. 首次启动时 Windows 防火墙会询问是否允许。**请在专用网络上允许**，否则其他设备无法连接。

需要 **Windows 10 2004 或更高版本 / Windows 11，64 位**。无需安装其他软件。

## 快速开始

1. 在**画面来源**中选择画面，在**音频来源**中打开要发送的声音。
2. 点击**开始串流**。
3. 在其他设备上打开**访问地址**中显示的地址 (例如 `http://192.168.0.10:47800`)，或扫描二维码。

如果同一网络还有其他人使用，请设置**访问 PIN**。

## 以手机或其他电脑作为来源

步骤显示在**画面来源 → 外部设备 → 连接设备**中。

| 设备 | 方式 | 操控 |
|---|---|---|
| Android 11 及以上 | 无线调试 (扫码配对)，画面和声音 | 触摸、键盘、剪贴板 |
| Android 5~10 | USB 调试线 | 同上 |
| iPhone · iPad | RTMP 直播应用 (例如 Larix Screencaster) | 蓝牙鼠标/键盘 (实验性) |
| PC · Mac · Chromebook | 通过网页共享屏幕 | – |
| 手机摄像头 | 网页 | – |

Android 连接文件 (约 11MB) 会在首次使用时从 [scrcpy](https://github.com/Genymobile/scrcpy) 官方发布版下载，并校验是否被篡改。接收 AirPlay 需要许可证不同 (GPL‑3.0) 的额外模块，未包含在内。

## 可选：GPU 运行库

如果有 NVIDIA Video Effects SDK 运行库，可以使用 NVIDIA RTX Video 超分辨率和帧生成。因许可证无法一同发布，请将文件放入**设置 → 打开附加组件文件夹 → `rtx-runtime`** 并重新启动。没有时使用内置方式处理。

## 更新

程序会在启动时和每四小时检查新版本，并在后台下载。不会中断串流，可随时重新启动，或在退出程序时安装。可在**设置**中关闭。

## 隐私

画面和声音只会发送到同一网络中连接的设备。程序只在两种情况下连接互联网：在 GitHub 检查更新，以及应您的要求下载 Android 文件。

## 无法连接时

- 两台设备必须连接同一路由器。访客 Wi‑Fi 通常会阻止设备之间互相访问。
- 在 **Windows 安全中心 → 防火墙和网络保护 → 允许应用通过防火墙** 中，确认当前网络类型 (专用或公用) 已允许 LocalStreamShare。
- 使用 5GHz Wi‑Fi 或有线连接可获得更低延迟。

所用开源软件的许可证可在程序的**设置 → 开源许可证**中查看。
