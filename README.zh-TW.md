# LocalStreamShare

<p align="center"><img src="https://raw.githubusercontent.com/hungbok/localstreamshare-releases/main/icon.png" width="112" alt="LocalStreamShare"></p>

[下載 Windows 版](https://github.com/hungbok/localstreamshare-releases/releases/latest) · [English](README.md) · [한국어](README.ko.md) · [日本語](README.ja.md) · [简体中文](README.zh-CN.md)

以超低延遲將**您選擇的畫面與聲音**串流到同一 Wi‑Fi/區域網路內的手機、電腦與電視。觀看端只需用瀏覽器開啟網址。開發者：**HungBok**

## 主要功能

- **只在您自己的網路內運作。** 影像從電腦直接傳送到觀看裝置 (WebRTC)。不需帳號，不經過外部伺服器，沒有時間限制。
- **畫面來源**：螢幕、單一視窗、擷取卡/攝影機 (不經過電腦螢幕直接串流)、影片檔案、手機或其他電腦的螢幕
- **音訊來源**：輸出裝置、僅特定程式 (或排除特定程式)、麥克風、擷取卡聲音。可分別設定音量並混合。
- 適合遊戲的**超低延遲預設**：硬體 H.264 · 60fps · 1080p，觀看端緩衝最小化
- **GPU 畫質增強**：超解析度 (FSR 1.0、Anime4K)、反鋸齒、降噪、畫格生成 (動態補間)、色彩校正
- **以手機作為來源**：Android 透過無線偵錯取得畫面、聲音並可操控 (不需安裝應用程式)；任何裝置都可用瀏覽器；iPhone 可用 RTMP 直播應用程式
- 預覽全螢幕、效能面板 (F3)、存取 PIN、連線用 QR 碼
- 支援韓文、英文、日文、簡體中文與繁體中文。觀看頁面依開啟裝置的語言顯示。

## 安裝

1. 從 [Releases](https://github.com/hungbok/localstreamshare-releases/releases/latest) 下載 `LocalStreamShare-Setup-x.y.z.exe` 並執行。
2. 選擇語言、安裝位置與捷徑。程式會為所有使用者安裝，並要求一次系統管理員權限。
3. 安裝程式沒有程式碼簽章，Windows SmartScreen 可能會發出警告。請確認檔案來自本頁面，然後選擇**其他資訊 → 仍要執行**。
   - 如果開啟了**智慧型應用程式控制** (部分新的 Windows 11 電腦)，Windows 會直接封鎖所有未簽章的程式。可在 **Windows 安全性 → 應用程式與瀏覽器控制** 中查看狀態。
4. 首次啟動時 Windows 防火牆會詢問是否允許。**請在私人網路上允許**，否則其他裝置無法連線。

需要 **Windows 10 2004 以上版本 / Windows 11，64 位元**。不需安裝其他軟體。

## 快速開始

1. 在**畫面來源**中選擇畫面，在**音訊來源**中開啟要傳送的聲音。
2. 按下**開始串流**。
3. 在其他裝置上開啟**連線位址**中顯示的網址 (例如 `http://192.168.0.10:47800`)，或掃描 QR 碼。

如果同一網路還有其他人使用，請設定**存取 PIN**。

## 以手機或其他電腦作為來源

步驟顯示在**畫面來源 → 外部裝置 → 連接裝置**中。

| 裝置 | 方式 | 操控 |
|---|---|---|
| Android 11 以上 | 無線偵錯 (掃碼配對)，畫面與聲音 | 觸控、鍵盤、剪貼簿 |
| Android 5~10 | USB 偵錯傳輸線 | 同上 |
| iPhone · iPad | RTMP 直播應用程式 (例如 Larix Screencaster) | 藍牙滑鼠/鍵盤 (實驗性) |
| PC · Mac · Chromebook | 透過網頁分享螢幕 | – |
| 手機相機 | 網頁 | – |

Android 連線檔案 (約 11MB) 會在首次使用時從 [scrcpy](https://github.com/Genymobile/scrcpy) 官方發行版下載，並驗證是否遭竄改。接收 AirPlay 需要授權不同 (GPL‑3.0) 的額外模組，未包含在內。

## 選用：GPU 執行階段

如果有 NVIDIA Video Effects SDK 執行階段，可以使用 NVIDIA RTX Video 超解析度與畫格生成。因授權無法一併發行，請將檔案放入**設定 → 開啟附加元件資料夾 → `rtx-runtime`** 並重新啟動。沒有時使用內建方式處理。

## 更新

程式會在啟動時與每四小時檢查新版本，並在背景下載。不會中斷串流，可隨時重新啟動，或在結束程式時安裝。可在**設定**中關閉。

## 隱私

畫面與聲音只會傳送到同一網路中連線的裝置。程式只在兩種情況下連線網際網路：在 GitHub 檢查更新，以及應您的要求下載 Android 檔案。

## 無法連線時

- 兩台裝置必須連接同一個路由器。訪客 Wi‑Fi 通常會阻止裝置之間互相存取。
- 在 **Windows 安全性 → 防火牆與網路保護 → 允許應用程式通過防火牆** 中，確認目前的網路類型 (私人或公用) 已允許 LocalStreamShare。
- 使用 5GHz Wi‑Fi 或有線連線可獲得更低延遲。

所用開放原始碼軟體的授權可在程式的**設定 → 開放原始碼授權**中查看。
