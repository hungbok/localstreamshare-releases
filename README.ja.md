# LocalStreamShare

<p align="center"><img src="https://raw.githubusercontent.com/hungbok/localstreamshare-releases/main/icon.png" width="112" alt="LocalStreamShare"></p>

[Windows版をダウンロード](https://github.com/hungbok/localstreamshare-releases/releases/latest) · [English](README.md) · [한국어](README.ko.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md)

同じWi‑Fi/LANにあるスマートフォン・PC・テレビへ、**選んだ画面と音だけ**を超低遅延で配信します。見る側はブラウザーでアドレスを開くだけです。開発: **HungBok**

## 主な機能

- **自分のネットワーク内で動作します。** 映像はPCから視聴端末へ直接送られます(WebRTC)。アカウント、外部サーバー、時間制限はありません。
- **画面ソース**: モニター、1つのウィンドウ、キャプチャーボード・ウェブカメラ(PC画面を経由せず直接配信)、動画ファイル、スマートフォンや他のPCの画面
- **音声ソース**: 出力デバイス、特定のアプリのみ(または特定のアプリ以外すべて)、マイク、キャプチャーボードの音。複数を個別の音量でミックスできます。
- ゲーム向けの**超低遅延プリセット**: ハードウェアH.264 · 60fps · 1080p、視聴側のバッファを最小化
- **GPUによる画質向上**: 超解像(NVIDIA DLSS / DLAA · NVIDIA RTX™ Video · AMD FSR™ · Intel® XeSS · Anime4K)、フレーム生成(NVIDIA VFG · DLSS Frame Generation · FSR 3 · モーション補間)、アンチエイリアス、ノイズ除去、色補正。必要なファイルはすべて同梱しています。
- **スマートフォンをソースに**: Androidはワイヤレス デバッグで画面・音声・操作(アプリ不要)、iPhone・iPadはAirPlay画面ミラーリングで、どの端末でもブラウザーから、RTMP配信アプリから
- **記憶します**: ウィンドウの位置、選んだソースと音量、アドレスとポート。選んだウィンドウ・機器・アプリが消えても、再び現れたら自動的に戻します。
- **バックグラウンドでも継続**: 最小化したウィンドウも選んで配信でき、配信中のウィンドウを最小化しても止まりません。
- 必要なら**インターネットからも接続**(初期状態はオフ): ルーターのポートを自動で開き、グローバルIP・ポート・QRコードを表示し、PINで保護します。
- プレビューの全画面表示(スマートフォンの操作パネル付き)、性能ダッシュボード(F3)、接続PIN、接続用QRコード
- 韓国語・英語・日本語・中国語(簡体字・繁体字)に対応。視聴ページは開いた端末の言語で表示されます。

## インストール

1. [Releases](https://github.com/hungbok/localstreamshare-releases/releases/latest)から`LocalStreamShare-Setup-x.y.z.exe`をダウンロードして実行します。
2. 言語を選び、使用許諾契約を確認してから、インストール先・ショートカットを選びます。すべてのユーザー向けにインストールされ、管理者権限を1回確認します。
3. コード署名がないため、Windows SmartScreenの警告が出ることがあります。このページから入手したファイルであることを確認し、**詳細情報 → 実行**を押してください。
   - **スマート アプリ コントロール**がオンの場合(一部の新しいWindows 11 PC)、署名のないプログラムは選択肢なくブロックされます。状態は**Windows セキュリティ → アプリとブラウザーの制御**で確認できます。
4. 初回起動時にWindowsファイアウォールの確認が表示されます。**プライベートネットワークで許可**しないと他の端末から接続できません。

**Windows 10 バージョン2004以降 / Windows 11、64ビット**が必要です。ほかにインストールするものはありません。ディスク容量は約1GB必要です。

## クイックスタート

1. **画面ソース**で画面を選び、**音声ソース**で配信する音をオンにします。
2. **配信を開始**を押します。
3. 他の端末で**接続アドレス**に表示されたアドレス(例: `http://192.168.0.10:47800`)を開くか、QRコードを読み取ります。

同じネットワークを他の人も使う場合は**接続PIN**を設定してください。

### 別のネットワークから見る

**設定 → 外部(インターネット)からのアクセスを許可**をオンにすると、ルーターのポートを開き(UPnP)、接続するグローバルIPとポートを表示します。ルーターが対応していない場合は、自分で転送するポートを表示します。外部からは**外部アクセスPIN**が必要で、視聴のみ可能です。グローバルIPのない回線では使えない場合があります。使わないときはオフにしてください。

## スマートフォン・他のPCをソースにする

**画面ソース → 外部機器 → 機器を接続**に手順が表示されます。

| 端末 | 方法 | 操作 |
|---|---|---|
| Android 11以降 | ワイヤレス デバッグ(QRペア設定)、画面と音声 | タッチ・キーボード・クリップボード |
| Android 5~10 | USBデバッグのケーブル接続 | 同上 |
| iPhone · iPad · Mac | AirPlay画面ミラーリング(実験的)またはRTMP配信アプリ(例: Larix Screencaster) | Bluetoothマウス・キーボード(実験的) |
| PC · Mac · Chromebook | ウェブページから画面共有 | – |
| スマートフォンのカメラ | ウェブページ | – |

Android接続ファイル([scrcpy](https://github.com/Genymobile/scrcpy)サーバーとadb)は同梱しています。AirPlayの受信は[UxPlay](https://github.com/FDH2/UxPlay)の非公式実装を使用し、Appleが提供するものではありません。Netflixなどの保護された映像はミラーリングされません。

## GPU機能

| 機能 | 必要なもの |
|---|---|
| NVIDIA DLSS / DLAA、RTX Video超解像、Video Frame Generation | NVIDIA RTX GPUと最新のドライバー |
| NVIDIA DLSS Frame Generation | NVIDIA RTX 40シリーズ以降 |
| AMD FSR 2 / 3、FSR 3 Frame Generation、Intel XeSS | 最近のGPUすべて (NVIDIA・AMD・Intel、DirectX 12) |
| AMD FSR 4 | AMD Radeon RX 9000シリーズ |
| FSR 1.0、Anime4K、モーション補間、アンチエイリアス、ノイズ除去 | すべてのGPU |

このPCで使えない項目は使用不可と表示されます。

## 更新

起動時と4時間ごとに新しいバージョンを確認し、バックグラウンドでダウンロードします。配信は中断されず、好きなときに再起動するか、終了時にインストールされます。**設定**でオフにできます。

## プライバシー

画面と音は、同じネットワークで接続した端末にのみ送信されます。アプリ自身がインターネットに接続するのは、GitHubでの更新確認だけです。外部アクセスを許可した場合に限り、グローバルIPを確認するサービス(ipifyなど)に接続し、インターネットからの接続を受け付けます。選んだソースなどの記憶内容はこのPCにのみ保存されます。NVIDIAのコンポーネントはNVIDIAドライバーを通じて更新されることがあります。

## 接続できないとき

- 両方の端末が同じルーターに接続されている必要があります。ゲストWi‑Fiは端末同士の通信を遮断することがあります。
- **Windows セキュリティ → ファイアウォールとネットワーク保護 → ファイアウォールによるアプリケーションの許可**で、現在のネットワークの種類(プライベートまたはパブリック)にLocalStreamShareが許可されているか確認してください。
- 遅延を抑えるには5GHz Wi‑Fiまたは有線接続を使用してください。

## ライセンス

LocalStreamShareはMITライセンスで無料です。同梱コンポーネントはそれぞれのライセンスに従い、インストール先の`licenses`に入っています(**設定 → ライセンスフォルダーを開く**)。

| コンポーネント | ライセンス |
|---|---|
| NVIDIA DLSS、NVIDIA RTX™ Video、NVIDIA Video Effects、CUDAランタイム | NVIDIA RTX SDKs License、NVIDIA Software License Agreement、NVIDIA Open Model License |
| AMD FidelityFX | AMDライセンス / MIT |
| Intel XeSS | Intel Simplified Software License |
| scrcpyサーバー、Android Debug Bridge | Apache License 2.0 |
| FairPlay.exe (UxPlay) | GPL‑3.0、ソースコードは`licenses\FairPlay\source` |
| Microsoft Visual C++ランタイム | Microsoftライセンス |
| Electron、Anime4Kなど | `THIRD_PARTY_NOTICES.txt` |

NVIDIAのコンポーネントはNVIDIA GPUを搭載したPCでのみ使用でき、個別に再配布することはできません。NVIDIA、AMD、Intel、Microsoft、Apple、Googleが保証または後援するプログラムではなく、商標は各社に帰属します。
