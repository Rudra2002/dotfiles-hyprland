<div align="center">

# 🌸**Apatheia Dot Files**🌸

![GitHub Repo stars](https://img.shields.io/github/stars/AmadeusWM/dotfiles-hyprland?style=for-the-badge&color=E08BCA) ![GitHub last commit](https://img.shields.io/github/last-commit/AmadeusWM/dotfiles-hyprland?style=for-the-badge&color=E08BCA) ![GitHub repo size](https://img.shields.io/github/repo-size/AmadeusWM/dotfiles-hyprland?style=for-the-badge&color=E08BCA)


<br/>

![screen_1](/assets/screenshots/ImagesShowcase.png)

<br/>

</div>

# Details
- **Compositor**: [Hyprland](https://github.com/hyprwm/Hyprland)
- **Top- and sidebar**: [eww](https://github.com/elkowar/eww)
- **Notifications**: [dunst](https://github.com/dunst-project/dunst)
- **Wallpaper Loader**: [swww](https://github.com/Horus645/swww)
- **Wallpaper**: `/themes/apatheia/wallapapers`
- **Terminal**: [kitty](https://github.com/kovidgoyal/kitty)
- **Search menu**: [wofi](https://github.com/uncomfyhalomacro/wofi)

# Usage

## 📦 Required dependencies:
Install these dependencies manually (Arch) 
```shell
hyprland-git nerd-fonts-complete wofi rofi wifi4wofi dunst eww-wayland swww swayidle swaylock-effects-git swaylockd sway-audio-idle-inhibit-git pamixer light papirus-icon-theme playerctl waybar-hyprland-git cava waybar-mpris-git kitty xdg-desktop-portal-wlr grim slurp wl-clipboard
```

## 🧙‍♂️ Setup Hyprland Config
### Default Theme
Copy all files from the repo to your hyprland config folder, and rename `_hyprland.conf` to `hyprland.conf` .
```bash
git clone git@github.com:AmadeusWM/dotfiles-hyprland.git
cd dotfiles-hyprland
cp -r ./* ~/.config/hypr
# Rename config file
mv ~/.config/hypr/_hyprland.conf ~/.config/hypr/hyprland.conf 
```

### Switching Primary Screen
Add this line to your config:
```conf
exec=~/.config/hypr/scripts/variables/set_env primary [ID_OF_PRIMAR_SCREEN] #0, 1, 2, ...
```

### Switching theme or config (Optional)
Assign the `source` parameter in the `hyprland.conf` to a different configuration file.

<details>
<summary style="font-weight: bold;" >
## ✨ Theming Other Applications
</summary>

### Default
The themes of other applications are saved in the `dots` folder.
`wofi`, `rofi`, `kitty` and `dunst` can be themed by copying the folders into `~/.config`
```bash
cp  ./dots/dunst ~/.config
cp  ./dots/wofi ~/.config
cp  ./dots/rofi ~/.config
cp  ./dots/kitty ~/.config
```

### Spotify (Spicetify)
Install spicetify. (AUR: `spicetify-cli`)
Copy `dots/spicetify` to `~/.config` (or wherever your spicetify configurations are stored)
Then:
```bash
cd "$(dirname "$(spicetify -c)")/Themes/Dribbblish"
mkdir -p ../../Extensions
cp dribbblish.js ../../Extensions/.
spicetify config extensions dribbblish.js
spicetify config current_theme Dribbblish color_scheme base
spicetify config inject_css 1 replace_colors 1 overwrite_assets 1
spicetify apply
```
### Discord (Better Discord)
install from AUR: `betterdiscordctl`

Copy `dots/BetterDiscord/Ultra.theme.css` to `~/snap/discord/145/.config/BetterDiscord/`

#### For Discord Installed With Snap
```bash
betterdiscordctl --d-install snap install 
```

### VS-code
The Apatheia theme can be found on the marketplace. 
Look up `Apatheia` from `Amadeus Wolf`

#### If You Want To Change It
You'll have to upload it to the vs-code marketplace.
Follow the docs:
1. Generate theme repository
    - https://code.visualstudio.com/api/extension-guides/color-theme#create-a-new-color-theme
2. Publish theme
    - https://code.visualstudio.com/api/working-with-extensions/publishing-extension#next-steps

### Firefox
#### Firefox Theme
1. in Firefox go to about:config. Change `toolkit.legacyUserProfileCustomizations.stylesheets` to "True"
2. Find your profile folder (go to about:profiles)
3. Copy the `chrome` folder from `dots/firefox` to the aforementioned profile folder.
4. Restart firefox, you theme should be updated

#### Tree Style Tabs
1. Install the Tree Style Tabs extension from [here](https://addons.mozilla.org/en-US/firefox/addon/tree-style-tab/)
2. Visit `Preferences` with `ctrl+shift+a>Tree Style Tab>Preferences`
3. Scroll to the bottom, and Press `Import` in `All Configs`
4. Import the `config.json` from `dots/firefox/treestyletab/config.json`
5. Then go to `Advanced` and scroll down
6. Choose `Load from file` and upload the following `Firefox Theming/treestyletab/treestyletab.css`

#### Night Tab
1. Install the nighttab extension from [here](https://addons.mozilla.org/en-US/firefox/addon/nighttab/)
2. Go to night tab settings (top right), and then the data tab
3. Import `dots/firefox/night-tab/night-tab.json`
4. You'll have to change the colors yourself if you change the theme from the default

### GTK Theme
For GTK: [Orchis-Theme](https://github.com/vinceliuice/Orchis-theme)
Edit the following files:
- `~/.config/gtk-3.0/settings.ini`
- `~/.config/gtk-4.0/settings.ini`
to:
```conf
[Settings]
gtk-application-prefer-dark-theme=1
gtk-theme-name = Orchis-Dark
```
and you might have to run: 
```bash
gsettings set org.gnome.desktop.interface color-scheme prefer-dark
```
### Eww Bar
Credits to https://github.com/taylor85345
Dependency: `eww-wayland`

</details>

<br/>

# ⌨️ Keybinds
- `SUPER+Z`: Prev orkspace
- `SUPER+X`: Next orkspace
- `SUPER+CTRL+M`: Quit Hyprland
- `SUPER+1,...9,0`: Switch workspace
- `ALT+1,...9,0`: Move window to workspace
- `SUPER+ALT+1,...9,0`: Move window to workspace (silent)
- `SUPER+B`: Switch Wallpaper
- `SUPER+V`: Open clipboard history
- `SUPER+T` or `CTRl+ALT+T`: Kitty
- `SUPER+F` or `CTRL+ALT+F`: Firefox
- `SUPER+O`: Obsidian
- `SUPER+E`: Nautilus
- `SUPER+A`: VS-code

# ⭐ Credits
- [Back777space](https://github.com/Back777space): for contributing🗿🗿🗿
- [Zenneh](https://github.com/zenneh): the Obsidian theme📔
- [Taylor85345](https://github.com/taylor85345): the well-organized dotfiles, and top-bar🧔‍♀️
- [flick0](https://github.com/flick0): inspiring hyprland-setup and useful scripts😍
- [Vaxry](https://github.com/vaxerski): HYPRLAND 🤍

# 🔨 TO-DO
- [x] Notifications (this maybe? https://www.reddit.com/r/unixporn/comments/sacxs3/oc_styled_notifications_using_dunst/)
- [x] Swappable wallpaper with wofi
example:
```bash
ls /home/amadeusw/.config/hypr/themes/apatheia/wallpapers | wofi --show dmenu
```
- [ ] Disable and Enable notifications
- [ ] Pull request Dunst: rounded icons
- [ ] Answer issue eww primary screen (first, try the command man): https://github.com/elkowar/eww/issues/382#issuecomment-1281693594
