LINK: https://fishshell.com/

YOUTUBE: https://youtu.be/QR5pANw7ZH4

**FISH INSTALL**

> FEDORA
```
sudo dnf install fish
```

> ARCO
```
sudo pacman -S fish
```

**MAIN CONFIG FILE**
```
~/.config/fish/config.fish
```

**CHANGE DEFAULT SHELL**
```
chsh -s /usr/bin/fish
```

**CHANGE ANOTHER USER SHELL**
```
sudo chsh -s /usr/bin/fish bob
```

**FASTFETCH**
```
micro ~/.config/fish/config.fish
```

> ADD at the end of the file
```
fastfetch
```

**REMOVE FISH GREETING**
```
micro ~/.config/fish/config.fish
```
```
set fish_greeting
```

**EXISTING PATHS UNDERLINED BY DEFAULT**

> REMOVE
```
set fish_color_valid_path
```

> PUT BACK
```
set fish_color_valid_path --underline
```

**MULTIPLE WILDCARDS - EXAMPLES**

```
l w*.j*
```

```
l /var/**.log
```

**LOOK OF THE FISH THEME IN TERMINAL**
```
fish_config theme show
```


**FISH MAN COMPLETITIONS**
```
fish_update_completions
```

**FISH HELP FROM TERMINAL**
```
help
```

**FISH CONFIG IN THE WEB BROWSER**
```
fish_config
```

