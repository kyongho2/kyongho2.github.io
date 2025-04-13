---
title: Fcitx5 Input Method Setup
---

# Fcitx5 Input Method Setup

## 1. Install Fcitx5 and Language Modules

```bash
sudo dnf install fcitx5 fcitx5-configtool \
fcitx5-gtk2 fcitx5-gtk3 fcitx5-gtk4 fcitx5-qt \
fcitx5-hangul fcitx5-mozc
```

## 2. Set Environment Variables

### Add the following to `~/.xprofile` or `~/.bashrc`:

```bash
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```

### Apply the changes:

```bash
source ~/.xprofile
# or
source ~/.bashrc
```

## 3. Enable Auto-Start

```bash
mkdir -p ~/.config/autostart
cp /usr/share/applications/org.fcitx.Fcitx5.desktop ~/.config/autostart/
```

## 4. Launch Fcitx5 Configuration Tool

```bash
fcitx5-configtool
```

## 5. Reboot or Log Out

Reboot or log out to apply changes.

## 6. Verify Input Method

```bash
echo $GTK_IM_MODULE
echo $QT_IM_MODULE
echo $XMODIFIERS
fcitx5-diagnose
```
