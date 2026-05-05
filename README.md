# Proton VPN symbolic icons
This is a fix for the lack of proper symbolic icons for Proton VPN's tray icons. By default, it uses the colorful icons, which does not fit in with the other monochrome UI icons.

The icons here were taken from [Papirus](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme).

### Before
[image]

### After
[image]

## Installation
Recommended:
```
git clone --depth 1 https://github.com/MoshiurRahmanAdib/ProtonVPN-symbolic-icons.git ~/.local/share/icons/ProtonVPN-symbolic
```

Or just copy the `ProtonVPN-symbolic` folder or clone this repo to your icons folder – `~/.local/share/icons/` for local installation, or `/usr/share/icons/` for system-wide.

## Usage
> [!NOTE]
> You should not apply this by itself as your icon theme, that will probably just make most of your icons show as missing, as this does not have any icons besides the Proton VPN ones.

There are a few ways you could apply it. Note that the changes probably will not reflect immediately. You can just log out and back in if you can't see the changes. (For me, quitting Proton VPN, changing the icon theme, and restarting Proton VPN also works.)

### Your icon theme inherit ProtonVPN-symbolic
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

> [!IMPORTANT]
> Again, NO SPACES.

### Copy-paste
You can also just copy the icons (including the symlinks) from here to the appropriate folders of the icon theme that you are using. You can check which directory is what in both's `index.theme`. 

## Notes
I have only tested it on GNOME, can't confirm if it works on other DEs. Let me know if you find any problems, or open a PR if you know a fix.