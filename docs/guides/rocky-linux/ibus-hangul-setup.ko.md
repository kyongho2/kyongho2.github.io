---
title: IBus 입력기 설치 가이드
---

# IBus 입력기 설치 가이드

## ibus-hangul 설치

```bash
sudo dnf install -y ibus-hangul
```

## Configure Input Method

1. Go to **Settings > Keyboard > Input Sources**.
2. Click the **“+” button**, then search for `Korean`.
3. Select `Korean (Hangul)` and add it.
4. Click the **gear icon** next to the input source.
5. For **Hangul Toggle Key**, select `ISO_Level3_Shift`.

> 💡 This is typically mapped to the right Alt key (Right Alt / AltGr).

## Apply Changes

Restart ibus or reboot the system:

```bash
ibus restart
# or
reboot
```

## Show Tray Icon (GNOME)

To show the input source indicator in the top panel:

```bash
gsettings set org.gnome.desktop.input-sources show-all-sources true
```
