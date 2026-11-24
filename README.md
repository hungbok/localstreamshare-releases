# LocalStreamShare

<p align="center"><img src="https://raw.githubusercontent.com/hungbok/localstreamshare-releases/main/icon.png" width="112" alt="LocalStreamShare"></p>

[Download for Windows](https://github.com/hungbok/localstreamshare-releases/releases/latest) · [한국어](README.ko.md) · [日本語](README.ja.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md)

Stream **only the screen and sound you choose** to phones, PCs and TVs on the same Wi‑Fi/LAN, with ultra low latency. Viewers just open an address in a browser. Developed by **HungBok**.

## Features

- **Runs entirely on your own network.** Video goes straight from your PC to the viewer (WebRTC). No account, no outside server, no time limit.
- **Screen sources**: a monitor, a single window, a capture card or webcam (sent directly, without passing through the PC screen), a video file, or the screen of a phone or another PC.
- **Audio sources**: an output device, a single app (or everything except one app), microphones and capture card audio. Mix several with separate volumes.
- **Ultra low latency preset** for games: hardware H.264, 60 fps, 1080p, minimal buffering on the viewer side.
- **Picture enhancement on the GPU**: super resolution (FSR 1.0, Anime4K), anti-aliasing, noise reduction, frame generation (motion interpolation) and color correction.
- **Phones as sources**: Android over Wireless debugging (screen, sound and control, no app to install), any device's browser, and RTMP broadcast apps on iPhone.
- Preview in full screen, performance dashboard (F3), access PIN, QR code for viewers.
- Korean, English, Japanese, Simplified and Traditional Chinese. The viewer page follows the language of the device it is opened on.

## Install

1. Download `LocalStreamShare-Setup-x.y.z.exe` from [Releases](https://github.com/hungbok/localstreamshare-releases/releases/latest) and run it.
2. Choose a language, folder and shortcuts. It installs for all users and asks for administrator permission once.
3. The installer is not code-signed, so Windows SmartScreen may warn you. Check that you downloaded it from this page, then choose **More info → Run anyway**.
   - If **Smart App Control** is on (some new Windows 11 PCs), Windows blocks every unsigned program and offers no such choice. Check it in **Windows Security → App & browser control**.
4. On first start Windows Firewall asks for permission. **Allow it on private networks**, or viewers cannot connect.

Requires **Windows 10 version 2004 or later / Windows 11, 64-bit**. Nothing else needs to be installed.

## Quick start

1. Choose a screen under **Screen source**, and turn on the sounds you want under **Audio sources**.
2. Press **Start streaming**.
3. On the other device, open the address shown under **Address** (for example `http://192.168.0.10:47800`) or scan the QR code.

Set an **Access PIN** if other people use the same network.

## Phones and other PCs as sources

**Screen source → External → Connect device** shows the steps.

| Device | How | Control |
|---|---|---|
| Android 11 or later | Wireless debugging (QR pairing), screen and sound | Touch, keyboard, clipboard |
| Android 5–10 | USB debugging cable | Same |
| iPhone · iPad | RTMP broadcast app (e.g. Larix Screencaster) | Bluetooth mouse/keyboard (experimental) |
| PC · Mac · Chromebook | Share the screen from a web page | – |
| Phone camera | Web page | – |

The Android connection files (about 11 MB) are downloaded from the official [scrcpy](https://github.com/Genymobile/scrcpy) release the first time, with a checksum check. Receiving AirPlay needs an extra module under a different license (GPL‑3.0) that is not included.

## Optional GPU runtimes

NVIDIA RTX Video super resolution and frame generation work if you have the NVIDIA Video Effects SDK runtime. It cannot be bundled for license reasons: put the files in **Settings → Open the add-ons folder → `rtx-runtime`** and restart. Without it the built-in methods are used.

## Updates

The app checks for a new version at startup and every four hours, and downloads it in the background. It never interrupts a stream: restart when you like, or it installs when you quit. You can turn this off in **Settings**.

## Privacy

Your screen and sound are sent only to the devices that connect on your network. The only internet connections the app makes are the update check on GitHub and, if you ask for it, the download of the Android files.

## If viewers cannot connect

- Both devices must be on the same router. Guest Wi‑Fi often blocks devices from reaching each other.
- In **Windows Security → Firewall & network protection → Allow an app through firewall**, check that LocalStreamShare is allowed for your network type (private or public).
- Use 5 GHz Wi‑Fi or a cable for the lowest latency.

Third-party licenses are listed in the app under **Settings → Open-source licenses**.
