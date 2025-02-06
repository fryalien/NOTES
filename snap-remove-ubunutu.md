# ALL UBUNTU FLAVORS
#remove snap
```
snap remove thunderbird firefox firmware-updater gnome-42-2204 core22 gtk-common-themes gtk-theme-breeze icon-theme-breeze bare snapd
```

```
sudo systemctl stop snapd
```

```
sudo apt remove --purge --assume-yes snapd gnome-software-plugin-snap
```

```
sudo rm -rf ~/snap
```

```
sudo rm -rf /snap
```

```
sudo rm -rf /var/snap
```

```
sudo rm -rf /var/lib/snapd
```

```
micro /etc/apt/preferences.d/nosnap.pref
```

```
Package: *
Pin: origin packages.snapcraft.io
Pin-Priority: -10
```

or 

```
echo 'Package: * Pin: origin packages.snapcraft.io Pin-Priority: -10' | sudo tee /etc/apt/preferences.d/nosnap.pref
```

```
sudo systemctl disable snapd
```

```
sudo systemctl mask snapd
```
