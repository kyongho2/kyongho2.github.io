---
title: Rocky Linux 9 Installation
---

# 🐧 Rocky Linux 9 Installation

This guide covers everything from installing **Rocky Linux 9** to performing essential desktop user configurations including **system updates**, **Korean input support**, and **Logitech receiver setup**.

---

## 💿 Installing Rocky Linux 9

1. **Download the ISO image from the official website**
   → [https://rockylinux.org](https://rockylinux.org)
   For desktop use, it's recommended to download the **DVD ISO** or **GNOME Desktop ISO**.

2. **Create a bootable USB**
   - Windows: Use [Rufus](https://rufus.ie/)
   - Linux/macOS: Use the `dd` command or `balenaEtcher`

3. **Start the installation**
   - Boot from the USB and select **“Install Rocky Linux 9”**
   - Set language, keyboard layout, timezone, and disk partition
   - Create a user account and set the root password
   - Reboot the system after installation is complete

> ⚠ During installation, choose **"Workstation"** or **"GNOME Desktop"** in the **“Software Selection”** step to enable a GUI environment.

---

## ✅ System Update

Update the system and apply the latest patches:

```bash
sudo dnf update -y
```

---

## 🔌 Logitech Receiver Setup

### Add the EPEL repository

```bash
sudo dnf install -y epel-release
```

### Install Solaar

```bash
sudo dnf install -y solaar
```

After installation, launch **Solaar** to view and configure your Logitech wireless devices.

---

## 🎉 All Set!

Rocky Linux 9 has been successfully installed and configured with essential settings.
Let me know if you need help with additional software or system customization.
