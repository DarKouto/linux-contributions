# 🐧 Linux Contributions

Personal log of Linux Contributions. Including maintaining AUR packages, hardware fixes, Nvidia boot issues, Kernel audio quirks, etc.

## 📦 AUR Packages

### 🎵 Lyra Music Desktop (AUR)
Created a PKGBUILD for the AppImage version of the **Lyra Music App** on the official repo: https://github.com/Lyra-Music-App/Lyra-Desktop-Releases

I asked the main developer [marf](https://github.com/marf) permission to upload the AUR version, which was granted.

- **Package URL:** [https://aur.archlinux.org/packages/lyra-music-bin](https://aur.archlinux.org/packages/lyra-music-bin)
- **Role:** Official maintainer of the lyra-music-bin package on the Arch User Repository. PKGBUILD development & system integration.
- **Features:** Multi-resolution icon support, FUSE2 integration, and KDE Plasma desktop optimization.

Now the users of Arch Linux and its derivatives can install it using the command:
```bash
yay -S lyra-music-bin
```

---

## 🛠️ Documented Fixes

### Index
| Device / System | Component | Status | Contribution Type |
| :--- | :--- | :--- | :--- |
| [**Acer Aspire V3-572G**](./acer-v3-572g-audio.md) | Audio (ALC283) | **Merged Upstream** | Formal Kernel Patch (Bugzilla) |
| [**Gigabyte G5 KF5**](./gigabyte-g5-kf5-audio.md) | Audio (ALC897) | **Merged (CachyOS)** | Kernel Quirk (SND_PCI_QUIRK) |
| [**Nvidia (Laptops)**](./nvidia-cachyos-boot-freeze.md) | Boot / Power Mgmt | **Resolved** | Bug Isolation & Package Revert |

### 1. [Acer Aspire V3-572G: Headset Mic Detection](./acer-v3-572g-audio.md)
Fixed a long-standing issue where the combo jack failed to detect external microphones or created "ghost" devices.
* **Impact:** Global support in the Mainline Linux Kernel.
* **Key Tech:** HDA Codec, Bugzilla, SND_PCI_QUIRK.

### 2. [Gigabyte G5 KF5 (2023): Audio Jack Fix](./gigabyte-g5-kf5-audio.md)
Resolved microphone detection issues on the Realtek ALC897 codec by implementing a hardware-specific quirk.
* **Impact:** Out-of-the-box support for CachyOS users.
* **Key Tech:** Modprobe, Kernel Maintainer Collaboration.

### 3. [Nvidia: Boot Freeze (cachyos-settings)](./nvidia-cachyos-boot-freeze.md)
Identified and helped resolve a critical boot freeze caused by a regression in power management parameters.
* **Impact:** Fixed boot stability for Nvidia laptop users on CachyOS.
* **Key Tech:** System Snapshots, Regression Testing, Collaboration with Peter Jung.
