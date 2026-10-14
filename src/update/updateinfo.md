<!-- iedegame-update: version=1.2610.1502 -->

<!-- iedegame-update: lang=ja -->

# iedeGAME サーバー 1.2610.1502

## 新しくなったところ

### セーブデータの同期

- サインインしてゲームを起動すると、**サーバーにある最新のセーブデータ**からプレイを再開できます。
  別の機器で遊んだ続きを、そのまま次の機器で遊べます。
- 遊び終わってエミュレーターを閉じると、**「エミュレーターのセーブデータでサーバーを更新しますか？」**
  と確認します。更新すると、次はどの機器からでもその続きから始められます。
  更新しない場合は、サーバーのセーブデータはそのまま残ります。
- Windows・macOS・Android・Linux Mobile（Anbernic製デバイスなど）のLocal Launcherで、
  **RetroArch**を使って遊んだ場合に機能します。
- セーブデータは**サインインしたアカウントごと**に分かれます。ゲストアカウントは複数人で
  共有する前提のため、同期の対象外です。

### NDSでは、Standaloneエミュレーターも試験的に使えます

- NDS（ニンテンドーDS）だけは、RetroArch以外の**Standaloneエミュレーター**でも同じ同期を
  試せるようになりました。対応するのは次のものです。

  | 機器 | エミュレーター |
  | --- | --- |
  | Windows | DeSmuME / melonDS |
  | macOS | DeSmuME |
  | Android | DraStic |

- **この機能は既定でOFFです。** Local Launcherの**「Standaloneエミュレーターのセーブデータ管理」**を開き、
  **「iedeGAMEによるNDSのStandaloneセーブデータの編集を許可する」**をONにしたときだけ動きます。
  Windowsは通知領域（タスクトレイ）のメニュー、macOSは設定画面、Androidはホーム画面から開けます。
- 許可は**機器ごと**に覚えます。ある機器でONにしても、ほかの機器はOFFのままです。
- **警告：許可すると、エミュレーターにある既存のセーブデータが削除・上書きされる場合があります。**
  必要なセーブデータは、許可する前にバックアップしてください。

### ご注意

- NDS以外のStandaloneエミュレーターは、セーブデータ同期の対象ではありません。
  ゲームの起動と、エミュレーター自身が保存するセーブデータは、これまでどおり使えます。
- NDSのStandaloneエミュレーターへの対応は**試験的なもの**です。すべてのエミュレーターの版や
  すべてのゲームで確認したものではありません。大切なセーブデータはバックアップをお願いします。

<!-- iedegame-update: lang=en -->

# iedeGAME Server 1.2610.1502

## What's new

### Save data synchronization

- Sign in and start a game, and play resumes from the **latest save data held on the server**.
  Where you left off on one device is where you start on the next.
- When you close the emulator, you are asked **"Update the server with the emulator save data?"**
  Update it, and you can carry on from that point on any of your devices. Decline, and the save
  data on the server is left as it was.
- This works in the Local Launcher on Windows, macOS, Android, and Linux Mobile (Anbernic
  devices and the like), for games played through **RetroArch**.
- Save data is kept **per signed-in account**. Guest accounts are meant to be shared between
  people, so they are left out of synchronization.

### For NDS, standalone emulators can be used too (experimental)

- For NDS (Nintendo DS) only, the same synchronization can now be tried with **standalone
  emulators** rather than RetroArch. The following are supported:

  | Device | Emulator |
  | --- | --- |
  | Windows | DeSmuME / melonDS |
  | macOS | DeSmuME |
  | Android | DraStic |

- **This is OFF by default.** It works only once you open **Standalone emulator save management**
  in the Local Launcher and turn on **Allow iedeGAME to edit NDS standalone save data**.
  You will find it in the notification area (tray) menu on Windows, in the settings window on
  macOS, and on the home screen on Android.
- The permission is remembered **per device**. Turning it on for one device leaves the others off.
- **WARNING: Allowing editing may delete or overwrite existing saves in the emulator.**
  Back up any save data you need before enabling this option.

### Please note

- Standalone emulators other than NDS ones are not covered by save data synchronization.
  Starting games, and the save data the emulator keeps by itself, work just as before.
- Support for NDS standalone emulators is **experimental**. It has not been checked against every
  emulator build or every game. Please keep backups of save data that matters to you.
