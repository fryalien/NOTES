**YOUTUBE:** https://youtu.be/3E90-JZZ_0M

**HOMEPAGE:** https://flathub.org/

**INSTALL FLATPAK:** https://flathub.org/setup

---

**INSTALL APPLICATION**
```
flatpak install librewolf
```

*OR*

```
flatpak install flathub io.gitlab.librewolf-community
```


**REMOVE APPLICAITON**
```
flatpak remove librewolf
```

*OR*

```
flatpak remove io.gitlab.librewolf-community
```

**RUN APPLICATION**
```
flatpak run io.gitlab.librewolf-community
```

**SEARCH FOR APPLICAITON**
```
flatpak search librewolf
```

**UPDATE ALL APPLICATIONS**
```
flatpak update
```

**LIST ALL INSTALLED APPLICAITONS**
```
flatpak list --app
```

**LIST ALL THE APPLICAITONS AND RUNTIMES**
```
flatpak list
```

**REMOVE ALL UNUSED RUNTIMES**
```
flatpak uninstall --unused
```

**LIST ALL INSTALLED APPS TO A FILE**
```
flatpak list --app > ~/Downloads/flatpak-list.md
```

**FLATPAK AUTO INSTALL**
```
flatpak install flathub md.obsidian.Obsidian -y
```

**FLATPAK INSTALL HISTORY**
```
flatpak history
```

**INFO ABOUT INSTALLED APPLICATION**
```
latpak info --show-extensions org.signal.Signal
```

**USER DATA**

~/.var/app

**FLATPAK CONFIG**

~/.local/share/flatpak

**SYSTEM WIDE CONFIG**

/var/lib/flatpak


**LIST FLATPAK REMOTES ("REPOSITORIES")**
```
flatpak remotes
```

**ADD FLATPAK REMOTE**
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

**REMOVE FLATPAK REMOTE**
```
flatpak remote-delete flathub
```

---

**FLATPAK DOCUMENTATION:** https://docs.flatpak.org/en/latest/introduction.html

**YOUTUBE:** https://youtu.be/3E90-JZZ_0M
