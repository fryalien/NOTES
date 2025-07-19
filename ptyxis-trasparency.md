**Set transparency in Ptyxis**

>Install.

```
sudo pacman -S ptyxis
```

>Get the UUID.

```
dconf read /org/gnome/Ptyxis/default-profile-uuid
```

'6f0e5478095e4811243d6d95686ba558'

>Apply transparency to that UUID.

dconf write /org/gnome/Ptyxis/Profiles/your_uuid/opacity 0.88

```
dconf write /org/gnome/Ptyxis/Profiles/6f0e5478095e4811243d6d95686ba558/opacity 0.88
```

**Flatpak version (must be developer version)**

>Chech which version is installed.

```
flatpak list | grep Ptyxis
```

>Install developer version.

```
flatpak install --user --from https://nightly.gnome.org/repo/appstream/org.gnome.Ptyxis.Devel.flatpakref
```

>Check UUID.
```
flatpak run --command=gsettings org.gnome.Ptyxis.Devel get org.gnome.Ptyxis.Devel default-profile-uuid
```

>Change transparency.

```
flatpak run --command=gsettings org.gnome.Ptyxis.Devel set org.gnome.Ptyxis.Devel.Profile:/org/gnome/Ptyxis/Devel/Profiles/$(flatpak run --command=gsettings org.gnome.Ptyxis.Devel get org.gnome.Ptyxis.Devel default-profile-uuid | cut -f2 -d\')/ opacity 0.88
```
