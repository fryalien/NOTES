**YOUTUBE:** https://youtu.be/yjyEaoi6qeM

---

**ARCH BASED INSTALLATION**

>Instalaltion from some desktop environment first install:

```
sudo pacman -S micro kitty thunar fish rofi-wayland hyprland
```

```
paru -S vscodium librewolf
```

**INSTALL DISPLAY MANAGER**

```
sudo pacman -S sddm
```

```
ssystemctl enable sddm
```

**IN HYPRLAND**

>Check your monitor:

```
hyprctl monitor all
```

>Remove the above line and set your resolution

```
monitor=Virtual-1,1920x1080@60,auto,auto
```

>Change app launcher

```
$menu = rofi -show drun
```

---

**INSTALL WALLPAPER - HYPRPAPER**

```
sudo pacman -S hyprpaper
```

>Create config file.

```
touch ~/.config/hypr/hyprpaper.conf
```

>Define your wallpaper.

```
preload = ~/.config/wallpapers/amongus.png
wallpaper = , ~/.config/wallpapers/amongus.png
```

>monitor can be set to put different wallpeprs on different monitor:

```
wallpaper = monitor, ~/.config/wallpapers/name-of-your-wallpaper.png
```

>Add it to you hyprland config.

```
exec-once = hyprpaper
```

---

**INSTALL FONTS for waybar**

```
sudo pacman -S ttf-font-awesome
```

**INSTALL WAYBAR**

```
sudo pacman -S waybar
```

---

**INSTALL HYPRPANEL**

LINK: https://hyprpanel.com/getting_started/installation.html

```
curl -fsSL https://bun.sh/install | bash && \
  sudo ln -s $HOME/.bun/bin/bun /usr/local/bin/bun
```

```
sudo pacman -S pipewire libgtop bluez bluez-utils btop networkmanager dart-sass wl-clipboard brightnessctl swww python gnome-bluetooth-3.0 pacman-contrib power-profiles-daemon gvfs libdbusmenu-gtk3
```

```
yay -S grimblast-git gpu-screen-recorder hyprpicker matugen-bin python-gpustat aylurs-gtk-shell-git
```

>Installs HyprPanel to `~/.config/ags`

```
git clone https://github.com/Jas-SinghFSU/HyprPanel.git && \
  ln -s $(pwd)/HyprPanel $HOME/.config/ags
```

>Installs the `JetBrainsMono NerdFonts` used for icons.

```
cd ~/.config/ags
```

```
./install_fonts.sh
```
---

**SCREEN LOCK - HYPRLOCK**

LINK: https://wiki.hyprland.org/Hypr-Ecosystem/hyprlock/

```
paru -S hyprlock
```

>Create config file.

```
touch ~/.config/hypr/hyprlock.conf
```

>Add a keybinding in hyprland.

```
bind = $mainMod, L, exec, hyprlock 
```

>Hyprlock catppuccin theme.
https://github.com/catppuccin/hyprlock

---

**IDLE COMPUTER - HYPRIDLE**

LINK: https://wiki.hyprland.org/Hypr-Ecosystem/hypridle/

```
paru -S hypridle
```

```
touch ~/.config/hypr/hypridle.conf
```

>Build a config from the homepage.

```
general {
  lock_cmd = pidof hyprlock || hyprlock
}

listener {
  timeout = 180 # 3 min
  on-timeout = loginctl lock-session
}
```

>Add to hyprland conf.

```
exec-once = hypridle
```

---

**YOUTUBE:** https://youtu.be/yjyEaoi6qeM
