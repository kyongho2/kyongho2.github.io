---
title: Installing Rocky Linux 9
---

# Installing Rocky Linux 9

## Step 1. Base Settings

**System Update**

```
sudo dnf update -y
```

**Hangul Settings**

1. Install ibus

```
sudo dnf install -y ibus-hangul
```

2. Keyboard Input Sources Settings

- Move `Settings > Keyoard > Input Sources`
- Click `+` Button
- Search `Korean`
- Click`Korean`
- Add `Korean (Hangul)`
- Click `Korean (Hangul)` Preferences Pop-up Menu
- Add `Hangul Toggle Key` >> ISO_Level3_Shift

**Logitech Receiver Settings**

```
sudo dnf install -y epel-release
sudo dnf install -y solaar
```
