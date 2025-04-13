---
title: Fcitx5 Additional Tips
---

# 💡 Fcitx5 Additional Tips

## Solving Chromium/Chrome Compatibility Issues

Fcitx5 generally works more reliably than IBus in Chrome or Chromium-based browsers. If your input method doesn't work properly in Chrome, switching to Fcitx5 often resolves the issue.

## Tray Icon Not Showing in GNOME

GNOME may not display tray icons by default. To show the Fcitx5 input method icon, install a GNOME extension like `TopIcons Plus`.

- [GNOME Extensions Site](https://extensions.gnome.org/)
- Search for: `TopIcons Plus`

## Applying a Theme

Fcitx5 supports various themes. For example, you can install the `fcitx5-material-color` theme for a clean and modern UI.

### Example Installation:

```bash
git clone https://github.com/hosxy/Fcitx5-Material-Color ~/.local/share/fcitx5/themes/Fcitx5-Material-Color
```

### How to Apply:

```bash
Open fcitx5-configtool > Go to the Appearance tab > Choose a theme
```

## Changing Input Method Switch Shortcuts

To use keys like `Shift + Space` or the `Hangul` key for language switching, go to the "Hotkey" tab in the Fcitx5 configuration tool and customize as needed.
