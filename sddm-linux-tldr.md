YOUTUBE: https://youtu.be/4amxR9MwiMY

---

**WHICH DISPLAY MANAGER IS RUNNING (systemd distro)**
```
grep 'ExecStart=' /etc/systemd/system/display-manager.service
```

**INSTALL**

> ARCH
```
sudo pacman -Sy sddm
```

> FEDORA
```
sudo snd install sddm
```

**ENABLE SDDM**
```
sudo systemctl enable sddm
```

OR

```
sudo systemctl disable lightdm && sudo systemctl enable sddm
```

**SDDM THEMES**
```
/usr/share/sddm/themes
```

**SDDM CONFIG FILE**
```
micro /etc/sddm.conf
```

```
[Theme]
Current=arcolinux-simplicity
```

**PREVIEW SDDM THEME**
```
sddm-greeter --test-mode --theme /usr/share/sddm/themes/arcolinux-simplicity
```


**DESKTOP SESSIONS**

> WAYLAND
```
ls -l /usr/share/wayland-sessions/
```

> X11
```
ls -l /usr/share/xsessions/
```

---

**SDDM LINKS:**

YOUTUBE
https://youtu.be/4amxR9MwiMY

GitHub source code

https://github.com/sddm/sddm

Arch Wiki

https://wiki.archlinux.org/title/SDDM

KDE Store - Themes

https://store.kde.org/browse?cat=101&ord=latest

kio-admin link

https://github.com/KDE/kio-admin


