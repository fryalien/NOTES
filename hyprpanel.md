**INSTALL PANEL/BAR - HYPRPANEL**

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
