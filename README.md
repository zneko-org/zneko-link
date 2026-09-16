<div align="center">

# ZNeko Link

<img src="zneko-link-logo.png" alt="ZNeko Link Logo" />

**The desktop companion for managing your Android devices.**

[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-blue.svg)]()
[![Latest Release](https://img.shields.io/github/v/release/zneko-org/zneko-link?label=latest&color=7c3aed)](https://github.com/zneko-org/zneko-link/releases)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-Support-ff5e5b?logo=ko-fi&logoColor=white)](https://ko-fi.com/gustavokei)

<p align="center">
  <a href="https://github.com/zneko-org/zneko-link/releases"><img src="https://raw.githubusercontent.com/rubenpgrady/get-it-on-github/refs/heads/main/get-it-on-github.png" alt="Get it on GitHub" height="55" /></a>
</p>

[What is ZNeko Link?](#what-is-zneko-link) • [Showcase](#showcase) • [Installation](#installation) • [How to Use](#how-to-use) • [Security](#security)

</div>

---

## What is ZNeko Link?

ZNeko Link is the Windows, macOS and Linux companion application for **[ZNeko Launcher](https://github.com/zneko-org/zneko-launcher)**.

It helps bring together tasks that would otherwise require USB transfers, cloud storage, synchronization tools, and manual file management.

---

## Showcase

<p align="center">
  <img src="show.png" alt="ZNeko Link interface showcase" style="max-width: 100%;">
</p>

---

## Installation

Download the latest installer for your operating system from the [Releases page](https://github.com/zneko-org/zneko-link/releases).

- **Windows**  
  Download and run the `.exe` installer. If Windows SmartScreen appears, click **More info → Run anyway**.

- **macOS**  
  Download the Universal `.dmg` (Apple Silicon and Intel), open it, and drag **ZNeko Link** into **Applications**.

  Because ZNeko Link is not distributed through the App Store, the first launch is blocked with *"Apple could not verify ZNeko Link is free of malware"*. This is macOS's standard warning for apps from independent developers. To open it:

  1. Click **Done** (not "Move to Trash").
  2. Open **System Settings → Privacy & Security**.
  3. Scroll all the way down to the **Security** section, where you will see *"ZNeko Link" was blocked to protect your Mac*.
  4. Click **Open Anyway** and confirm.

  This is only needed once; afterwards the app opens normally.

- **Linux**  
  Download the `.AppImage` for your architecture: `x86_64` for regular PCs, or `aarch64` for ARM machines (Raspberry Pi, ARM Chromebooks, Linux VMs on Apple Silicon). Make it executable and run it; there is nothing to install, and updates are applied from inside the app:

  ```bash
  chmod +x ZNeko-Link-x86_64.AppImage
  ./ZNeko-Link-x86_64.AppImage
  ```

  AppImages need FUSE, which every mainstream desktop distribution ships. If yours does not, run it with `./ZNeko-Link-x86_64.AppImage --appimage-extract-and-run` instead.

---

## How to Use

1. Open ZNeko Link on your computer.
2. Select an empty or existing folder on your computer to act as your ZNeko library root.
3. Once selected, ZNeko Link will automatically manage the following structure inside that folder:
   - `roms/`: Stores your platform folders and game files.
   - `backups/`: Stores files exported from or prepared for import into ZNeko Launcher.
   - `filelist.json`: A generated manifest used to browse the available library.
4. Create subfolders for your platforms (e.g., `roms/gba/`, `roms/psx/`) and place your game ROMs inside them.
5. Click **"Start Sharing"**.
6. Connect your Android device and computer to the same local network.
7. Open ZNeko Launcher. It will attempt to discover and connect to your PC automatically on boot. If it doesn't connect, you can go to **Settings > Backups** in the app to connect manually.
8. The first time a device connects, ZNeko Link asks you to **approve the device**. A confirmation code is shown on both screens, so approve only if they match, then press **Codes match** on the Android device. Approved devices are remembered and can be removed at any time from the ZNeko Link window.
9. Browse your available library from the Android device and choose what to transfer.

No manual IP address is normally required. ZNeko Launcher searches the local network and discovers ZNeko Link automatically.

---

## Security

Access to the shared folder is protected by **device pairing**: the first time a device connects, you approve it in the ZNeko Link window by comparing a code shown on both screens, then confirm **Codes match** on the Android device. Desktop approval alone does not grant access. Only devices that complete both steps can browse, transfer, or modify anything. Every other device on the network is rejected.

- **You are in control.** Approved devices are listed in the ZNeko Link window and can be removed at any time, which revokes their access immediately.
- **Local transfers are encrypted.** Pairing, library browsing, ROM transfers, and backups use HTTPS. The launcher pins Link's certificate after you compare the verification code shown on both screens.
- **Nothing leaves your network.** There are no accounts, no cloud, and no third-party servers involved.

> [!NOTE]
> ZNeko Link uses a persistent self-signed certificate because local IP addresses cannot use an ordinary public web certificate. The verification code shown during first pairing authenticates that certificate, and the launcher pins its full fingerprint for later connections. There is no plaintext fallback. As common sense, keep the shared folder to game-related files, and keep independent backups of saves you care about.
