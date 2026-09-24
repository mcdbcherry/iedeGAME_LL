<!-- iedegame-update: version=1.2609.2421 -->

<!-- iedegame-update: lang=ja -->

# iedeGAME サーバー 1.2609.2421

## 新しくなったところ

### お気に入りを登録できるようになりました

- ゲームのカードを**右クリック（スマートフォン/タブレットでは長押し）**すると、
  「お気に入りに追加」「お気に入りから削除」のメニューが出ます。
  ROM選択・検索結果・履歴・お気に入りの、どの画面のカードからでも操作できます。
- お気に入りに入れたゲームは、カードのプレビュー画像の左上に★が付きます。
- ブラウザーのトップ画面に「お気に入り」を追加しました。「履歴」の隣にあります。
- お気に入りは**アカウントごと**に保存します。ご自分のアカウントでサインインするとお使いいただけます。
  未サインインのときと、共有のゲストアカウントでは使用できません（トップ画面では灰色で表示されます）。
- サーバーアプリのメニューにも「お気に入り」を追加しました。**全員分のお気に入り**を確認でき、
  利用者での絞り込みと、表示中のお気に入りの削除ができます。

### 履歴が利用者ごとになりました

- ブラウザーの「履歴」には、**サインインしているご自身が遊んだゲーム**だけが表示されます。
  サインインしていない場合は、サインインせずに遊んだ分が表示されます。
- サーバーアプリのメニューに「履歴」を追加しました。**全員分の履歴**を新しい順に確認でき、
  利用者での絞り込みと、表示中の履歴の削除ができます。
- 1人あたりに残す件数（既定50件）も、この画面から変更できます。

### ROMフォルダの変更を見て、検索インデックスを自動で更新します

- サーバーアプリのトップ画面で「ROMフォルダの変更を監視して自動更新する」を有効にすると、
  ROMを追加・削除したときに検索インデックスが自動で更新されます（既定は無効）。
- まとめて更新するまでの待ち時間（既定5分）も指定できます。大量のROMをコピーしている間に
  何度も更新が走ることはありません。
- ネットワークドライブなど変更のお知らせを受け取れない場所は、定期的に確認します。

### BIOSの状態を確認できるようになりました

- サーバーアプリのメニューに「BIOSの確認」を追加しました。機種ごとに、必要なBIOSが
  置かれているか、内容が正しいかを一覧で確認できます。
- ブラウザー側でも、BIOSが足りない機種のROM一覧とプレイ画面に注意書きが出ます。
- 確認の結果でゲームの起動が止まることはありません。

### ゲーム情報とカバー画像の自動取得

- サーバーアプリの「プレビュー画像設定」で「画像とゲーム情報の自動取得」を有効にすると、
  gamelist.xmlやプレビュー画像が足りないゲームの情報とカバー画像を取得します（既定は無効）。
- 取得中に画面を離れても処理は続き、取得できた件数はその場で表示に反映されます。

### Local Launcher

- macOS版向けのLocal Launcherを追加しました。
- ニンテンドーDSで、Android版はmelonDS/DraStic、macOS版はDeSmuMEのスタンドアロン版を
  選べるようになりました。
- セーブデータの同期が、エミュレーターのコアごとの保存ファイルに対応しました。

### そのほか

- サインイン中の表示を、チェックマーク付きの「サインイン済み」に変更しました。
  ユーザー名はメニューの最下部に表示されます。

<!-- iedegame-update: lang=en -->

# iedeGAME Server 1.2609.2421

## What's new

### Games can be added to favorites

- **Right-click** a game card (**long-press** on a phone or tablet) to open a menu with
  **Add to favorites** / **Remove from favorites**. It works on the cards of the ROM list,
  search results, history and favorites pages alike.
- A star is shown at the top left of the preview image of every game in your favorites.
- A **Favorites** card was added to the browser's top page, next to **History**.
- Favorites are kept **per account**. Sign in with your own account to use them. They are not
  available while signed out or with the shared guest account (the card is greyed out there).
- A **Favorites** item was added to the server app menu as well. It lists **everyone's favorites**,
  can be filtered by user, and the favorites shown can be deleted.

### History is now per user

- The **History** page in the browser now shows only the games **you** played while signed in.
  When you are not signed in, it shows the games played without signing in.
- A new **History** item was added to the server app menu. It lists **everyone's history**,
  newest first, can be filtered by user, and the listed entries can be deleted.
- The number of entries kept per user (50 by default) can also be changed there.

### ROM folders can be watched, so the search index updates itself

- Turn on **"Watch ROM folders and update automatically"** on the server app's home screen, and the
  search index is rebuilt whenever ROMs are added or removed (off by default).
- You can also set how long to wait after a change (5 minutes by default), so copying a large number
  of ROMs does not trigger repeated updates.
- Folders that cannot report changes, such as network drives, are checked periodically instead.

### You can now check your BIOS files

- A new **BIOS Check** item was added to the server app menu. For each system it shows whether the
  required BIOS files are in place and whether their contents are correct.
- In the browser, a note also appears on the ROM list and play screen of systems with missing BIOS.
- Games are never blocked from starting because of this check.

### Automatic download of game info and cover art

- Turn on **"Use automatic download"** in the server app's **Preview Image Settings** to download
  game info and cover art for games missing from gamelist.xml and your image folders (off by default).
- The download keeps running when you leave the screen, and the counts update as items are fetched.

### Local Launcher

- A macOS version of the Local Launcher was added.
- For Nintendo DS you can now choose standalone emulators: melonDS / DraStic on Android and
  DeSmuME on macOS.
- Save data sync now handles per-core save files.

### Other changes

- The signed-in indicator now shows a check mark with "Signed in", and the user name moved to the
  bottom of the menu.
