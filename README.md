# iedeGame Local Launcher (iedeGameLL)

> [!IMPORTANT]
> **iedeGAME LL (Local Launcher) requires iedeGAME Server running on Windows 11.**
> **The client device must connect to iedeGAME Server over the network.**
> **iedeGAME LL cannot run games on its own.** Install and start iedeGAME Server first,
> then connect the launcher device to that server.
>
> **iedeGAME LL（Local Launcher）の使用には、Windows 11で動作するiedeGAME Serverが必要です。**
> **LLを使用する端末から、iedeGAME Serverへネットワーク経由で接続する必要があります。**
> **iedeGAME LLだけではゲームを実行できません。** 先にiedeGAME Serverを導入・起動してください。

`iedeGameLL` (iedeGAME Local Launcher) is a companion application for **iedeGAME Server for Windows 11**.
It launches games using RetroArch, or a supported standalone emulator, installed on the client device.

By default, iedeGAME Server runs games in the browser using the JavaScript/WebAssembly-based EmulatorJS.
After installing iedeGameLL on a client device, you can use the device's native RetroArch installation
(or, for some systems, a standalone emulator) instead of EmulatorJS.

The launcher supports English and Japanese UI, notifications, and error messages.
The default language is English; select your preferred language in the launcher settings.
All platform versions use the same iedeGAME application icon.

## About iedeGAME Server

For an overview, screenshots, and setup instructions for iedeGAME Server, visit the following page:

[Emulator Server — iedeGAME for Windows](https://mcdb.jp/iedegame.html)

## Supported Platforms

| Platform | Release file | How it works |
|---|---|---|
| Windows x64 | `iedeGameLL.exe` | Runs in the system tray and launches RetroArch or a standalone emulator |
| Android | `iedeGameLL.apk` | Launches RetroArch or a standalone emulator when invoked by iedeGAME |
| Linux desktop x64 | `iedeGameLL-Linux-x64.tar.gz` | Ubuntu amd64; settings window, URI handler, RetroArch and supported standalone emulators |
| Linux desktop arm64 | `iedeGameLL-Linux-arm64.tar.gz` | Raspberry Pi OS 64-bit desktop; settings window, URI handler, RetroArch and supported standalone emulators |
| Linux Mobile | Device-specific packages listed below | Selected Anbernic handhelds running stock Linux firmware; built-in browser and on-device RetroArch |
| macOS 13+ | `iedeGameLL-macos.dmg` | Universal app (Apple Silicon / Intel); launches RetroArch or a standalone emulator |

iOS and iPadOS are not currently supported.

## Requirements

- iedeGAME Server running on Windows 11
- A client device with network access to that running iedeGAME Server
- RetroArch installed on the client device, and the RetroArch cores required by the systems you want to play,
  or a supported standalone emulator for systems that offer one (see **Standalone Emulators** below)
- .NET 8 Desktop Runtime for the Windows version

Linux desktop packages are self-contained and do not require a separate .NET Runtime installation.
Linux Mobile uses the supported device's existing RetroArch and cores; use the package for your exact model.

iedeGameLL does not include RetroArch, standalone emulators, RetroArch cores, ROMs, or BIOS files.

## Basic Usage

1. Install or extract the appropriate iedeGameLL release on the client device.
2. Install RetroArch and the required cores (or a supported standalone emulator) on the client device.
3. Open iedeGAME Server in a web browser.
4. Under **iedeGAME Settings — Player**, select **Use Local Launcher**.
5. Select a game from the ROM list. iedeGameLL will receive the request and launch it with the local RetroArch
   installation, or with the standalone emulator configured for that system.

The player selection is stored separately for each browser and device, not as a server-wide setting.
The default player is **JavaScript (EmulatorJS)**.
Linux Mobile uses its bundled browser and the device's RetroArch; follow the device setup below.

## Standalone Emulators

For some systems, iedeGameLL can launch a standalone emulator instead of RetroArch. This is configured per
system in the launcher's core settings (Windows: tray menu "Core settings by system"; Android, Linux desktop, and macOS: the
same setting in their own settings screen).

- **PlayStation 2** — Windows/Linux x64/macOS: PCSX2. Android: ARMSX2 and NetherSX2/AetherSX2.
- **GameCube / Wii** — Windows/Linux desktop/macOS/Android: Dolphin.
- **Linux desktop additional options** — PlayStation: DuckStation; Nintendo DS: DeSmuME or melonDS.

Available choices depend on the platform and CPU architecture. Linux Mobile supports RetroArch only.

When a standalone emulator is selected, iedeGameLL only downloads the ROM from the server. BIOS files, auxiliary
files, and RetroArch save-data sync do not apply. Configure BIOS and system files in the standalone emulator.
Save sharing is a separate, optional feature for supported emulators (see **Save Data**).

## Windows

1. Place `iedeGameLL.exe` in any suitable folder and run it.
2. The launcher remains available in the system tray and handles `iedegame-launcher://` requests.
3. It automatically searches for RetroArch in Windows App Paths, standard installation locations, Steam, Scoop, and `PATH`.

When RetroArch is configured, a `✓` appears on the right side of **Configure RetroArch** in the tray menu.
If a portable RetroArch installation cannot be detected, use this menu item to select `retroarch.exe` manually.

## Android

1. Install `iedeGameLL.apk` on the device.
2. Install the latest official version of RetroArch (and the required cores) or a supported standalone emulator.
3. On the first launch from iedeGAME, approve the notification permission and confirm that you trust the server.

Some Android or RetroArch versions may restrict launches from external applications. If RetroArch does not start,
update it to the latest version and confirm that the required core is installed.

## Linux Desktop

Download `iedeGameLL-Linux-x64.tar.gz` for Ubuntu amd64, or `iedeGameLL-Linux-arm64.tar.gz` for
Raspberry Pi OS 64-bit. Extract the entire archive into a permanent, user-writable folder.
From that folder, run the installer in a logged-in desktop session (no `sudo` required):

```bash
sh install.sh
```

The installer registers the application and the `iedegame-launcher://` URI handler.
If you move the extracted folder, run `sh install.sh` again from its new location.
For labwc desktops, avoid spaces and special characters in the installation path.

Open `iedeGameLL` without arguments, or run the following command, to configure RetroArch, core selection,
and standalone executables:

```bash
./iedeGameLL settings
```

The desktop version detects native RetroArch installations and supports the official Flatpak package
`org.libretro.RetroArch` and Snap installations. Detection and game compatibility depend on the installed
package and cores. Executables and AppImages selected manually must have execute permission.
PCSX2 is available only on x64; standalone emulator operation and performance on Raspberry Pi remain unverified.
Xbox, Xbox 360, and PlayStation 3 standalone launching are not supported on Linux.

The OS must provide the native dependencies for .NET 10, X11/XWayland, libx11, libice, libsm, fontconfig,
Japanese fonts for Japanese UI, xdg-utils, and zenity for progress and confirmation dialogs.
Wayland sessions require XWayland. Raspberry Pi OS requires a 64-bit userspace and a desktop environment;
32-bit and Lite installations are not supported.

Use `./iedeGameLL --diagnose` to check the environment and core detection, or `./iedeGameLL --show-log`
to view the diagnostic log. Packages include a matching `.sha256.txt` checksum file.

## Linux Mobile — Anbernic Handhelds

Linux Mobile is a separate launcher for the following stock-firmware devices. It includes a browser for
connecting to iedeGAME Server and launches games using the handheld's installed RetroArch and compatible cores.
It does not use EmulatorJS or standalone emulators.

| Device | Package | Firmware used for verification |
|---|---|---|
| RG ARC-S / RG ARC-D | `iedeGameLL-LinuxMobile-anbernic-rg-arc-stock-arm64.tar.gz` | Stock Linux, Buildroot `2021.05-git`, build `-g22787cd0` |
| RG SP | `iedeGameLL-LinuxMobile-anbernic-rg-sp-stock-arm64.zip` | Stock OS `20260624` |
| RG 35XXSP | `iedeGameLL-LinuxMobile-anbernic-rg-35xxsp-stock-arm64.zip` | Stock OS `20260522` |
| RG 34XX | `iedeGameLL-LinuxMobile-anbernic-rg-34xx-stock-arm64.tar.gz` | Stock OS `20260526` |
| RG CubeXX | `iedeGameLL-LinuxMobile-anbernic-rg-cubexx-stock-arm64.zip` | Stock OS `20260525` |

RG SP, RG 35XXSP, RG 34XX, and RG CubeXX are development versions with limited device/game verification.
Use only the package for your exact model and stock OS; packages are not interchangeable, including RG SP
and RG 35XXSP. Other firmware versions and custom firmware are not covered by the verification above.
Compare the archive's SHA-256 with its accompanying `.sha256.txt` before installation.

### Installation

1. Connect the handheld and the Windows 11 PC running iedeGAME Server to the same LAN.
2. Shut down the handheld before removing its microSD card and extract the package on your PC.
3. **RG ARC:** merge the extracted `ports` folder into the ROM partition root, reinsert the card,
   then select **Ports → iedeGAME** in EmulationStation. Allow at least 500 MB of free space for installation.
4. **RG SP / RG 35XXSP / RG 34XX / RG CubeXX:** copy the entire extracted `Roms` folder to the TF2 card root.
   Keep the stock OS card in TF1, insert TF2, and select **Application Center → Apps → TF-2 →
   iedeGAME-LocalLauncher**. The first launch performs setup automatically.
5. Keep both TF1 and TF2 inserted for the Apps-based devices, and leave the copied package folders on TF2;
   they are used during normal operation, updates, and repair. Reserve space in both internal storage and TF2
   for setup and downloaded games. For RG SP, use at least an 8 GB TF2 card (32 GB or more recommended)
   with about 4 GiB free; RG 34XX recommends 32 GB or more with at least 8 GiB free.

### First Launch and Settings

Enter the server URL, for example `http://192.168.1.10:8787/`, choose English or Japanese, and select
**Test Connection and Save**. Once connected, select a game from the server's ROM list.
The launcher downloads the required data, starts RetroArch, and returns to the server screen after the game exits.

Use the directional pad to navigate, **A** to confirm, **B** to go back, and the **Menu** button to open
Local Launcher settings. The settings screen provides the server address, connection history, core selection,
and an option to start iedeGAME on boot. It also shows the launcher version and Wi-Fi IPv4 address.
The settings screen can open while the server is unavailable, but playing games requires a server connection.

## macOS

1. Open `iedeGameLL-macos.dmg` and drag **iedeGAME Local Launcher.app** onto the **Applications** folder.
2. The app is not code-signed with a Developer ID, so the first time you open it, Control-click the installed
   app and choose **Open** to allow it to run.
3. Opening the app registers the `iedegame-launcher://` URL handler and shows its settings window.

The settings window lets you configure the RetroArch location, core/standalone-emulator selection per system,
the URL handler, trusted servers, display language, and diagnostic log. The app has no menu-bar icon; it runs
only while its window or an in-progress launch is active.

RetroArch is auto-detected from `/Applications`, `~/Applications`, and Spotlight bundle-ID lookup, or you can
select it manually.

## Save Data

When signed in to iedeGAME, supported RetroArch save data can be downloaded from the server before a game
starts on Windows, Linux desktop, macOS, and Linux Mobile. Save sharing depends on the core and save format.
Linux Mobile checks for changed saves every 30 seconds during play. If unsent changes remain when RetroArch
exits, it asks whether to upload them; the default is **Do not update**. Declined or failed uploads remain local
and are not automatically retried.

Android does not provide the same automatic RetroArch synchronization because application storage is isolated.
Windows, macOS, and Android also offer experimental save sharing for selected standalone emulators, with
explicit setup and access permissions. The new save-sharing option is off by default; launching an emulator
does not by itself enable sharing. On Android, return to the launcher after quitting the game and confirm
completion to back up supported saves; some emulators require manual export/import.

Linux desktop supports opt-in Nintendo DS save sharing with native DeSmuME and a compatible server.
Standalone melonDS save sharing and other standalone save sharing are not supported on Linux desktop.
Linux Mobile supports RetroArch save sharing only.

## Security and Important Notes

- A new iedeGAME Server is used only after the user explicitly trusts it.
- ROM and BIOS data can only be downloaded from the same server origin that issued the launch request.
- Downloaded data is validated by file size and SHA-256 hash.
- iedeGameLL does not update itself automatically. Download new versions from GitHub Releases.
- Use ROMs, BIOS files, and other game data in accordance with applicable laws and the rights holder's terms.

## Release Files

Download the appropriate file for your platform from GitHub Releases:

- `iedeGAME-server-win-x64.zip` — iedeGAME Server for Windows 11 x64 (required to use Local Launcher)
- `iedeGameLL.exe` — Windows x64
- `iedeGameLL.apk` — Android
- `iedeGameLL-Linux-x64.tar.gz` — Linux desktop, Ubuntu amd64
- `iedeGameLL-Linux-arm64.tar.gz` — Linux desktop, Raspberry Pi OS 64-bit
- `iedeGameLL-macos.dmg` — macOS 13+ (Apple Silicon / Intel universal app)
- Device-specific `iedeGameLL-LinuxMobile-anbernic-…-stock-arm64` packages — see **Linux Mobile** above

Linux desktop and Linux Mobile archives have accompanying `.sha256.txt` files for checksum verification.
Download the package for your OS, CPU architecture, and (for Linux Mobile) exact device model.
