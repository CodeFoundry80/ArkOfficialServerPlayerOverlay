# ARK Player Overlay

A lightweight Windows overlay for **ARK: Survival Ascended** that automatically detects the Official ARK server you are currently connected to and displays live server information without modifying or injecting into the game.

Developed by **CodeFoundry**  
Written & tested by **.dodgeman**  
Discord: **@.dodgeman**

---

## About

YOU WILL NEED TO RUN THIS PROGRAM AS ADMIN! This is so that ETW can determine what server you are currently on. If you do not run as admin you will not get updated player numbers, or the server information you are on.

ARK Player Overlay was created to provide useful server information while playing **ARK: Survival Ascended** without requiring you to manually select or configure the server you are playing on.

Once ARK is running and you connect to a supported Official server, the overlay automatically determines which server you joined and displays its current information.

The overlay is designed to remain lightweight, unobtrusive, and independent from the game itself.

---

## Features

- **Automatic Official Server Detection**
- **Live Player Population**
- **Lightweight Transparent Overlay**
- **Click-Through Overlay**
- **Movable Overlay Position**
- **Automatic Server Information Updates**
- **No Manual Server Selection Required**
- **No Hardcoded Server IP Addresses**
- **No Packet Capture Drivers Required**
- **No Game File Modification**
- **No DLL Injection**
- **No Game Memory Modification**

---

## Automatic Server Detection

ARK Player Overlay automatically identifies the Official server that your running `ArkAscended.exe` process is communicating with.

The application uses Windows networking information to identify the remote server endpoint associated with ARK and compares it against the current Official ARK server directory.

This allows the overlay to determine the server automatically without requiring the player to enter:

- Server name
- Server IP address
- Server port
- Map
- Server number

The Official server directory is periodically refreshed so server information can remain current.

---

## Important

> **ARK Player Overlay currently supports Official ARK: Survival Ascended servers only.**

**Unofficial, private, and local servers are NOT currently supported.**

The application does **NOT** inject into, modify, or alter ARK game files or game memory.

ARK Player Overlay is **NOT** a cheat or game modification. It operates as a separate Windows application and displays information in its own transparent overlay window.

---

## Administrator Permission

ARK Player Overlay currently requires **Administrator privileges** for automatic server detection.

This is required because the application uses Windows Event Tracing for Windows (**ETW**) networking information to determine which server the ARK process is communicating with.

If the application is not running with the required permissions, automatic server detection may not function.

---

## How It Works

At a high level:

```text
ArkAscended.exe
      ↓
Detect running ARK process
      ↓
Monitor ARK network activity using Windows ETW
      ↓
Identify remote server IP and port
      ↓
Compare endpoint with Official ARK server directory
      ↓
Identify the Official ARK server
      ↓
Display live information in the overlay
```

No packet capture driver such as Npcap or WinPcap is required.

---

## Usage

1. Start **ARK Player Overlay**.
2. Start **ARK: Survival Ascended** if it is not already running.
3. Join an Official ARK server.
4. The overlay will automatically detect the server.
5. Current server information and player population will appear in the overlay.

ARK can be started either before or after the overlay. The overlay will detect the ARK process when it becomes available.

---

## Overlay Controls

The overlay is designed to stay out of the way while playing.

When locked, the main overlay area allows mouse input to pass through to the game.

Use the overlay controls when you need to:

- Move the overlay
- Change overlay settings
- Adjust its appearance or position

---

## Server Information

Official ARK server information is obtained from the Official ARK: Survival Ascended server directory.

The directory is periodically refreshed while the application is running.

This means the overlay does not rely on a manually maintained list of hardcoded Official server addresses.

---

## Privacy

ARK Player Overlay does not need to inspect ARK game memory or modify game files to determine your server.

Server detection is based on network activity associated with the running `ArkAscended.exe` process and the publicly available Official ARK server directory.

---

## Current Limitations

Currently:

- Official ARK: Survival Ascended servers are supported.
- Unofficial servers are not supported.
- Private servers are not supported.
- Local servers are not supported.
- Administrator privileges are required for automatic server detection.
- Server/player information depends on the availability and accuracy of the Official ARK server directory.

Additional functionality may be added in future versions.

---

## Requirements

- Windows
- ARK: Survival Ascended
- Administrator privileges
- Internet connection
- Microsoft .NET 8 Desktop Runtime

---

## Building From Source

ARK Player Overlay is a Windows WPF application built using **.NET 8**.

### Development Environment

- Visual Studio 2022
- .NET 8
- WPF
- Windows

### NuGet Dependency

The project uses:

```text
Microsoft.Diagnostics.Tracing.TraceEvent
```

for Windows ETW network event monitoring.

Because kernel ETW networking events require elevated permissions, Visual Studio should be started **as Administrator** when debugging the server-detection functionality.

---

## Disclaimer

ARK Player Overlay is an independent community project.

It is not affiliated with, endorsed by, sponsored by, or associated with **Studio Wildcard**, **Snail Games**, or the developers/publishers of **ARK: Survival Ascended**.

ARK, ARK: Survival Ascended, and related names and trademarks belong to their respective owners.

Use of this software is at your own discretion.

---

## Author

**CodeFoundry**

Written & tested by **.dodgeman**

Discord: **@.dodgeman**

For bug reports, problems, or feedback, please use GitHub Issues or contact me on Discord.

---

## License

See the `LICENSE` file for licensing information.
