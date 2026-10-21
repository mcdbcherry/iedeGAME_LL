<!-- iedegame-update: version=1.2610.2200 -->

<!-- iedegame-update: lang=ja -->

# iedeGAME サーバー 1.2610.2200

## 新しくなったところ

### 新しい機種への対応

- **Capcom CPS1・CPS2・CPS3、Neo Geo CD** に対応しました。Local Launcherから本体のRetroArchで起動できます。
- ご利用の端末に対応した最新版のLocal Launcherへ更新してください。

### Miyoo Mini Plusへの対応拡張

- Miyoo Mini Plusで、**アーケード（Arcade）・Capcom CPS1・CPS2・CPS3・Neo Geo** のゲームをLocal Launcherから起動できるようになりました。
- **PlayStation・PCエンジンCD・メガCD・Neo Geo CD** にも対応しました。

## これまでの更新内容

### Local LauncherがMiyoo Mini Plusに対応

- **Miyoo Mini Plus（Onion 4.3.1-1）** 向けのLocal Launcherに対応しました。サーバーのライブラリからゲームを選び、必要なROMを取得して本体のRetroArchでプレイできます。
- シンプルなリストUIで、機種選択・検索・履歴・お気に入り・ランキングを利用できます。表示言語は日本語・英語に対応しています。
- Miyoo Mini Plus版は専用UIを使用し、テーマ変更には対応していません。

### バージョン 1.2610.2200：サーバーの配布形態をインストーラー形式に変更

- iedeGAME サーバーの配布形態をインストーラー形式に変更しました。ダウンロードしたインストーラーを実行し、画面の案内に従ってインストールできます。

### PC版UIで一部コントローラーに対応

- PC版（Windows／macOS／デスクトップLinux）のブラウザー画面を、PCに接続した一部のコントローラーで操作できるようになりました。Linux Mobile版は従来の操作方法を使用します。
- 十字キー／左スティックで項目を移動し、決定・戻る・メニュー操作ができます。対応する操作方法は **Settings** で確認できます。
- ブラウザーが非アクティブな間は入力を無視します。Local Launcherなどから戻ったときは、一度ボタン・スティックを離すと操作を再開します。
- ブラウザーが標準配列として認識するコントローラーが対象です。利用には基本的にHTTPSまたはlocalhostでのアクセスが必要です。

### 新しいテーマ「Retro Panorama」を追加

- **Settings → Themes** から、新しいテーマ **Retro Panorama** を選べるようになりました。
- TOP画面では機種ごとの背景画像とコントローラー画像、機種名・発売年・ゲーム数を表示し、画面下のロゴを左右に動かして機種を切り替えられます。
- 画面右側に機種の特徴・紹介文を表示します。紹介文は日本語・英語の言語切り替えに対応しています。
- ROM選択画面と機種別ランキングにも、その機種の背景画像を暗めに表示します。
- 背景画像は縦横比を保って画面いっぱいに表示し、四辺が黒へフェードします。機種を切り替えると背景もフェードで切り替わります。

バージョン 1.2610.1815

### クライアントのテーマ変更に対応

- クライアントの **Settings → Themes** から、テーマ・配色・画面の表示形式を変更できるようになりました。
- **Default・Retro Showcase・Retro Glass** の3つのテーマを選べます。
- Top画面は一覧・カルーセル、ROM選択画面はタイル・詳細・カルーセルから表示形式を選べます。
- 設定はクライアントごとに保存されるため、同じサーバーを利用していても、それぞれ好みの見た目で使えます。

テーマ機能に対応していない古いLinux Mobile版Local Launcherでは、画面表示や操作が正しく動作しないことがあります。**最新版への更新をおすすめします。**

<!-- iedegame-update: lang=en -->

# iedeGAME Server 1.2610.2200

## What's new

### Support for additional systems

- Added support for **Capcom CPS1, CPS2, CPS3, and Neo Geo CD**. Launch games through Local Launcher using RetroArch on your device.
- Update to the latest Local Launcher for your device.

### Expanded support for Miyoo Mini Plus

- On Miyoo Mini Plus, Local Launcher can now launch games for **Arcade, Capcom CPS1, CPS2, CPS3, and Neo Geo**.
- Added support for **PlayStation, PC Engine CD, Sega CD, and Neo Geo CD**.

## Previous updates

### Local Launcher now supports Miyoo Mini Plus

- Local Launcher now supports **Miyoo Mini Plus running Onion 4.3.1-1**. Choose a game from your server library, download the required ROM, and play with the device's RetroArch.
- The simple list-based interface includes system selection, search, history, favorites, and rankings. Both English and Japanese are supported.
- The Miyoo Mini Plus version uses a dedicated interface and does not support changing themes.

### Version 1.2610.2200: Server distribution now uses an installer

- iedeGAME Server is now distributed as an installer. Run the downloaded installer and follow the on-screen instructions to install the server.

### PC interface support for selected controllers

- You can now navigate the browser interface on a PC (Windows, macOS, or desktop Linux) with selected controllers connected to that PC. Linux Mobile continues to use its existing controls.
- Use the D-pad or left stick to move between items, and controller buttons to select, go back, or open menus. See **Settings** for the controls.
- Controller input is ignored while the browser is inactive. After returning from Local Launcher or another app, release the buttons and sticks to resume navigation.
- Requires a controller that the browser recognizes with a standard button layout. Access through HTTPS or localhost is generally required.

### New Retro Panorama theme

- You can now choose **Retro Panorama** from **Settings → Themes**.
- The Top screen displays platform artwork, a controller image, the platform name, release year, and game count. Move left or right through the logos at the bottom to switch platforms.
- Platform introductions appear on the right and follow your Japanese or English language setting.
- ROM browsing and platform ranking screens use a dimmed version of the same platform artwork.
- Background artwork fills the screen while keeping its aspect ratio, with all four edges fading to black. Switching platforms also fades between backgrounds.

Version 1.2610.1815

### Customize your client's theme

- You can now change the theme, color scheme, and view layout from **Settings → Themes** on your client.
- Choose from three themes: **Default, Retro Showcase, and Retro Glass**.
- Choose a list or carousel for the Top screen, and tile, detailed, or carousel views when browsing ROMs.
- Settings are saved per client, so everyone connected to the same server can use their own preferred look.

Older versions of Local Launcher for Linux Mobile that do not support themes may not display or operate correctly. **We recommend updating to the latest version.**
