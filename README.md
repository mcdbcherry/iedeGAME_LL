# iedeGameLL

`iedeGameLL` (iedeGAME Local Launcher) is a companion application for **iedeGAME Server for Windows**.
It launches games using RetroArch, or a supported standalone emulator, installed on the client device.

By default, iedeGAME Server runs games in the browser using the JavaScript/WebAssembly-based EmulatorJS.
After installing iedeGameLL on a client device, you can use the device's native RetroArch installation
(or, for some systems, a standalone emulator) instead of EmulatorJS.

The launcher displays its UI, notifications, and error messages in Japanese when the operating system UI language
is Japanese. English is used for all other operating system languages.
All platform versions use the same iedeGAME application icon.

## About iedeGAME Server

For an overview, screenshots, and setup instructions for iedeGAME Server, visit the following page:

[Emulator Server — iedeGAME for Windows](https://mcdb.jp/iedegame.html)

## Supported Platforms

| Platform | Release file | How it works |
|---|---|---|
| Windows x64 | `iedeGameLL.exe` | Runs in the system tray and launches RetroArch or a standalone emulator |
| Android | `iedeGameLL.apk` | Launches RetroArch or a standalone emulator when invoked by iedeGAME |
| Linux x64 | `iedeGameLL.tar.gz` | Launches RetroArch through a registered URI handler |
| macOS 13+ | `iedeGameLL-macos.dmg` | Universal app (Apple Silicon / Intel); launches RetroArch or a standalone emulator |

iOS and iPadOS are not currently supported.

## Requirements

- iedeGAME Server for Windows
- A client device that can connect to the iedeGAME Server
- RetroArch installed on the client device, and the RetroArch cores required by the systems you want to play,
  or a supported standalone emulator for systems that offer one (see **Standalone Emulators** below)
- .NET 8 Desktop Runtime for the Windows version

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

## Standalone Emulators

For some systems, iedeGameLL can launch a standalone emulator instead of RetroArch. This is configured per
system in the launcher's core settings (Windows: tray menu "Core settings by system"; Android and macOS: the
same setting in their own settings screen).

- **PlayStation 2** — Windows/Android/macOS: PCSX2. Android additionally supports ARMSX2 and NetherSX2/AetherSX2.
- **GameCube / Wii** — macOS: Dolphin.

When a standalone emulator is selected, iedeGameLL only downloads the ROM from the server. BIOS files, auxiliary
files, and RetroArch save-data sync do not apply; configure and manage BIOS and save data inside the standalone
emulator itself.

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

## Linux

Extract `iedeGameLL.tar.gz`, make the executable runnable, and register the URI handler:

```bash
chmod +x ./iedeGameLL
./iedeGameLL --install-protocol
```

If RetroArch cannot be detected automatically, specify its executable path:

```bash
./iedeGameLL --configure-retroarch /path/to/retroarch
```

The Linux version supports standard RetroArch installations, the official Flatpak package
`org.libretro.RetroArch`, and Snap installations. Standalone emulators are not supported on Linux.

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

When signed in to iedeGAME, the Windows, Linux, and macOS versions can download RetroArch SRAM from the server
before a game starts. After RetroArch exits, you can confirm whether the updated save data should be uploaded
to the server.

Automatic save synchronization is not currently available on Android, because Android isolates each
application's storage from other applications. It is also unavailable when a standalone emulator is used on
any platform.

## Security and Important Notes

- A new iedeGAME Server is used only after the user explicitly trusts it.
- ROM and BIOS data can only be downloaded from the same server origin that issued the launch request.
- Downloaded data is validated by file size and SHA-256 hash.
- iedeGameLL does not update itself automatically. Download new versions from GitHub Releases.
- Use ROMs, BIOS files, and other game data in accordance with applicable laws and the rights holder's terms.

## Release Files

Download the appropriate file for your platform from GitHub Releases:

- `iedeGameLL.exe` — Windows x64
- `iedeGameLL.apk` — Android
- `iedeGameLL.tar.gz` — Linux x64
- `iedeGameLL-macos.dmg` — macOS 13+ (Apple Silicon / Intel universal app)
