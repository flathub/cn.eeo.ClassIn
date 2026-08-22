# ClassIn unofficial Flatpak wrapper

## Description

This is an unofficial Flatpak wrapper for ClassIn. 

Since ClassIn only officially provides `.deb` packages (which cannot be installed directly on Red Hat, SUSE, Arch, Gentoo-based, or immutable Linux distributions), this wrapper packages and extracts the official `.deb` binaries directly within the Flatpak sandbox.

## ⚠️ Known Issues
  - **Screen sharing does not work on Wayland:** This is an upstream issue from ClassIn (EEO). The client lacks QtWayland and xdg-desktop-portal implementation, resulting in a black screen when attempting to share. A temporary workaround is running your session on X11, or use WMs or DEs that support it if your current DE removed X11 support (I will recommend WMs, for example, Openbox or i3).
  
If you encounter any other issues, please report them on [GitHub Issues](https://github.com/flathub/cn.eeo.ClassIn/issues).

## 🚀 Quick Start

### Requirements

Before installing or building this package, ensure your system meets the following requirements:

- **Flatpak**: `flatpak` 1.12 or above (if it too old you can [compile it](https://github.com/flatpak/flatpak).)
- **Display Server**: X11 (recommended) or Wayland (with limitations)
- **Architecture**: `x86_64` or `aarch64`
- **flatpak-builder** *(only required if building from source)*: `flatpak-builder` 1.2 or above

### Installing Flatpak:

- **Debian / Ubuntu:**
  ```bash
  sudo apt update && sudo apt install flatpak
  ```

- **Fedora / Red Hat:**
  ```bash
  sudo dnf install flatpak
  ```

- **Arch Linux / Manjaro:**
  ```bash
  sudo pacman -Syu flatpak
  ```

- **openSUSE (Leap / Tumbleweed):**
  ```bash
  sudo zypper in flatpak
  ```

- **Gentoo:**
  ```bash
  sudo emerge --ask sys-apps/flatpak 
  ```

- **Set up Flathub repository:**
  ```bash
  flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
  ```

### Install from Flathub:
```bash
flatpak install flathub cn.eeo.ClassIn
```

### Build from source

- **Debian / Ubuntu:**
  ```bash
  sudo apt update && sudo apt install flatpak-builder
  ```

- **Fedora / Red Hat:**
  ```bash
  sudo dnf install flatpak-builder
  ```

- **Arch Linux / Manjaro:**
  ```bash
  sudo pacman -Syu flatpak-builder
  ```

- **openSUSE (Leap / Tumbleweed):**
  ```bash
  sudo zypper in flatpak-builder
  ```

- **Gentoo:**
  ```bash
  sudo emerge --ask dev-util/flatpak-builder
  ```

- **Install the Sdk:**
  ```bash
  flatpak install flathub org.freedesktop.Platform//25.08 org.freedesktop.Sdk//25.08
  ```

- **Locally build a Flatpak package :**
  ```bash  
  flatpak-builder --user --install --force-clean build-dir cn.eeo.ClassIn.json
  ```
*Note: You can remove flatpak-builder and the Sdk runtime after building or they are no longer needed.*

### Running ClassIn
```bash
flatpak run cn.eeo.ClassIn
```

## 🤝 Contributing

Contributions are always welcome! You can help by:
- Reporting issues (crashes, problems, missing fonts/libs).
- Submitting PRs to update the runtime version or the wrapper.
- Improving metadata or manifest.

Want to become a **co-maintainer**? If you use ClassIn on Linux regularly, you can join in and help maintain this package! See [this issue](https://github.com/flathub/cn.eeo.ClassIn/issues/5) for more info.

Feel free to open an issue or submit a PR anytime!

## 📄 License

This wrapper is licensed under the GPL-3.0-only license.

ClassIn is a registered trademark of Empower Education Online Ltd. (EEO). This project is community-maintained and is not affiliated with, supported, or endorsed by EEO.
