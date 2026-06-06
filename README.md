# Proton VPN symbolic icons
This is a simple fix for the lack of proper symbolic icons for Proton VPN's tray icons. By default, it uses the colorful icons, which does not fit in with the other monochrome UI icons. This solves that, and it can be used together with any icon theme.

> [!IMPORTANT]
> For non-Flatpak users, [see this](#for-non-flatpak-users)

The icons here were taken from [Papirus](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme).

Screenshots:
- **After**
<img width="500" height="281" alt="new" src="https://github.com/user-attachments/assets/58aeea87-8d43-4a7b-ac1a-0c6d5e3fd7ac" />

- **Before**
<img width="500" height="281" alt="original" src="https://github.com/user-attachments/assets/0ca2d09d-ce1b-4c39-bc7d-d2417636a723" />

## Installation
Recommended:
```
git clone --depth 1 https://github.com/MoshiurRahmanAdib/ProtonVPN-symbolic-icons.git ~/.local/share/icons/ProtonVPN-symbolic
```

Or just copy the `ProtonVPN-symbolic` folder or clone this repo to your icons folder – `~/.local/share/icons/` for local installation, or `/usr/share/icons/` for system-wide.

### For non-Flatpak users
Symbolic icons are only supperted in the [Flatpak version](https://flathub.org/en/apps/com.protonvpn.www) of Proton VPN.
If you do not use the Flatpak, try making [these changes](https://github.com/flathub/com.protonvpn.www/blob/47f57d55cc9897a31ac8d0a6411def15cddfe1c4/patches/proton-vpn-gtk-app/fix-tray-icons.patch) to `/usr/lib/python3.14/site-packages/proton/vpn/app/gtk/widgets/main/tray_icon.py` and `/usr/lib/python3.14/site-packages/proton/vpn/app/gtk/widgets/main/tray_indicator.py`.
> [!NOTE]
> **I did not try it yet**; if anyone does, let me know if it works.

## Usage
> [!NOTE]
> You should not apply this by itself as your icon theme, that will probably just make most of your icons show as missing, as this does not have any icons besides the Proton VPN ones.

There are a few ways you could apply it. Note that the changes probably will not reflect immediately. You can just log out and back in if you can't see the changes. (For me, quitting Proton VPN, changing the icon theme, and restarting Proton VPN also works.)

### Your icon theme inherit ProtonVPN-symbolic (Recommended)
The simplest is to just edit the `index.theme` of the icon theme you are using, adding `ProtonVPN-symbolic` (or whatever the folder name is) to the `Inherits` field (before anything that could override it). For example,

`.../[icon theme]/index.theme`:
```
[Icon Theme]
...
Inherits=ProtonVPN-symbolic,...,hicolor
...
```

> [!IMPORTANT]
> DO NOT PUT SPACES, if you don't want to spend 4 hours like me trying to find why the icons are broken.

### ProtonVPN-symbolic inherit your icon theme
Alternatively, you can add the name of the icon theme you want to use to the `index.theme`. For example,

`ProtonVPN-symbolic/index.theme`:
```
[Icon Theme]
Inherits=Adwaita
...
```
Again, **NO SPACES**.

### Copy-paste
You can also just copy the icons (including the symlinks) from here to the appropriate folders of the icon theme that you are using. You can check which directory is what in both's `index.theme`. 

## Notes
I originally made this for my personal use, and have only tested it on GNOME. I can't confirm if it works on other DEs. Let me know if you find any problems, and feel free to open a PR if you know a fix.

There could be a better way to achieve this, but I don't know of any. This is just the simplest way I found to patch this annoying inconsistency 😅
