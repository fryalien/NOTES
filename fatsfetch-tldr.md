---

**YOUTUBE:** https://youtu.be/PisSiVyktdM

---

**LINKS:**
https://github.com/fastfetch-cli/fastfetch
https://github.com/fastfetch-cli/fastfetch/tree/dev/presets
https://github.com/fastfetch-cli/fastfetch/tree/dev/presets/examples

---

**INSTALL**

> ARCO
```
sudo pacman -S fastfetch
```

> FEDORA
```
sudo dnf install fastfetch
```

---

**GENERATE CONFIG FILE** in ~/.config/fastfetch
```
fastfetch --gen-config
```

**LOAD CUSTOM FILE**
```
fastfetch --load-config /path/to/config_file
```

---

**SHOW ONLY HARDWARE**
```
fastfetch -c hardware
```

**PRINT LOGOS**
```
fastfetch --print-logos
```

**USE LOGO**
```
fastfetch --logo sparky
```
> name of the logo is from the previous command (--print-logos)

**EXAMPLE**
```
fastfetch -c hardware -l sparky
```

```
fastfetch --logo ~/.config/fastfetch/freebsd-logo.jpg
```

**ARCH JOKE**
```
fastfetch -c hardware -l arch
```

**USE CERTAIN COLOR**
```
fastfetch --color blue
```

**COLORS 1-9, 5 BLINKING**
```
fastfetch --color 5
```

**HELP - BUNCH OF OPTIONS**
```
fastfetch --help
```

**All filesytem paths can be:**
 * Absolute
 * Relative to the current working directory
 * Relative to any of the directories listed by fastfetch --list-data-paths + /logos
 For example, the file ~/.local/share/fastfetch/logos/shrek can simply be referenced as shrek.

```
fastfetch --list-data-paths
```

---


**PRESETS**
https://github.com/fastfetch-cli/fastfetch/tree/dev/presets
https://github.com/fastfetch-cli/fastfetch/tree/dev/presets/examples


**PREVIEW PRESETS**

```
fastfetch --load-config ~/.config/fastfetch/presets/all.jsonc
```

```
fastfetch --load-config ~/.config/fastfetch/presets/btw.jsonc
```

```
fastfetch --load-config ~/.config/fastfetch/presets/ci.jsonc
```

```
fastfetch --load-config ~/.config/fastfetch/presets/hardware.jsonc
```

```
fastfetch --load-config ~/.config/fastfetch/presets/neofetch.jsonc
```

```
fastfetch --load-config ~/.config/fastfetch/presets/paleofetch.jsonc
```

```
fastfetch --load-config ~/.config/fastfetch/presets/software.jsonc
```

```
fastfetch --load-config examples/2.jsonc
```

```
fastfetch --load-config examples/3.jsonc
```

```
fastfetch --load-config examples/4.jsonc
```

```
fastfetch --load-config examples/5.jsonc
```

```
fastfetch --load-config examples/6.jsonc
```

```
fastfetch --load-config examples/7.jsonc
```

```
fastfetch --load-config examples/8.jsonc
```

```
fastfetch --load-config examples/9.jsonc
```

```
fastfetch --load-config examples/10.jsonc
```

```
fastfetch --load-config examples/11.jsonc
```

```
fastfetch --load-config examples/12.jsonc
```

```
fastfetch --load-config examples/13.jsonc
```

---

# SIXEL (SIX PIXELS)

> ARCO
```
sudo pacman -S libsixel
```

**img2sixel**
```
img2sixel name-of-the-photo.jpg
```

---

**YOUTUBE:** https://youtu.be/PisSiVyktdM

---
