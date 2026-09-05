# iedeGameLL

`iedeGameLL` (iedeGAME Local Launcher) is a companion application for **iedeGAME Server for Windows**.
It launches games with RetroArch installed on the client device.

By default, iedeGAME Server runs games in the browser using the JavaScript/WebAssembly-based EmulatorJS.
After installing iedeGameLL on a client device, you can use the device's native RetroArch installation and
its cores instead of EmulatorJS.

## About iedeGAME Server

For an overview, screenshots, and setup instructions for iedeGAME Server, visit the following page:

[Emulator Server — iedeGAME for Windows](https://mcdb-cherry.com/2026/08/23/%e3%82%a8%e3%83%9f%e3%83%a5%e3%83%ac%e3%83%bc%e3%82%bf%e3%82%b5%e3%83%bc%e3%83%90%e3%83%bc-iedegame-for-win/)

## Supported Platforms

| Platform | Release file | How it works |
|---|---|---|
| Windows x64 | `iedeGameLL.exe` | Runs in the system tray and launches RetroArch |
| Android | `iedeGameLL.apk` | Launches RetroArch when invoked by iedeGAME |
| Linux x64 | `iedeGameLL.tar.gz` | Launches RetroArch through a registered URI handler |

iOS and iPadOS are not currently supported.

## Requirements

- iedeGAME Server for Windows
- A client device that can connect to the iedeGAME Server
- RetroArch installed on the client device
- The RetroArch cores required by the systems you want to play
- .NET 8 Desktop Runtime for the Windows version

iedeGameLL does not include RetroArch, RetroArch cores, ROMs, or BIOS files.

## Basic Usage

1. Install or extract the appropriate iedeGameLL release on the client device.
2. Install RetroArch and the required cores on the client device.
3. Open iedeGAME Server in a web browser.
4. Under **iedeGAME Settings — Player**, select **Local RetroArch**.
5. Select a game from the ROM list. iedeGameLL will receive the request and launch it with the local RetroArch installation.

The player selection is stored separately for each browser and device, not as a server-wide setting.
The default player is **JavaScript (EmulatorJS)**.

## Windows

1. Place `iedeGameLL.exe` in any suitable folder and run it.
2. The launcher remains available in the system tray and handles `iedegame-launcher://` requests.
3. It automatically searches for RetroArch in Windows App Paths, standard installation locations, Steam, Scoop, and `PATH`.

When RetroArch is configured, a `✓` appears on the right side of **Configure RetroArch** in the tray menu.
If a portable RetroArch installation cannot be detected, use this menu item to select `retroarch.exe` manually.

## Android

1. Install `iedeGameLL.apk` on the device.
2. Install the latest official version of RetroArch and the required cores.
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
`org.libretro.RetroArch`, and Snap installations.

## Save Data

When signed in to iedeGAME, the Windows and Linux versions can download RetroArch SRAM from the server before a
game starts. After RetroArch exits, you can confirm whether the updated save data should be uploaded to the server.

Automatic save synchronization is not currently available on Android because Android isolates each application's
storage from other applications.

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
