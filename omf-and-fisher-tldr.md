YOUTUBE: https://youtu.be/21ksdyl4x5Y

---

# INSTALL PACKAGES

> ARCO
```
sudo pacman -S inetutils powerline-fonts ttf-dejavu ttf-hack-nerd fzf fd bat
```

> FEDORA
```
sudo dnf install powerline-fonts fzf bat fd-find fontawesome-fonts-all dejavu-fonts-all  
```

```
https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/Hack.zip
```

---

# OMF

LINK: https://github.com/oh-my-fish/oh-my-fish
THEMES: https://github.com/oh-my-fish/oh-my-fish/blob/master/docs/Themes.md

**INSTALL OMF**
```
curl https://raw.githubusercontent.com/oh-my-fish/oh-my-fish/master/bin/install | fish
```

**OMF COMMON COMMANDS**


**OMF install plugin/theme**
```
omf install name|url|user/repo
```

> example
```
omf install agnoster
```

**OMF update**
```
omf update
```

**OMF list all packages**
```
omf list
```

**OMF list Themes**
```
omf theme
```

**OMF Apply Themes**
```
omf theme <theme_name>
```

**OMF remove package**
```
omf remove <name>
```

**RELOAD OMF AND ALL THE PLUGINS**
```
omf reload
```

**UNINSTALL OMF**

```
omf destroy
```

```
read> yes
```

---

# FISHER

LINK: https://github.com/jorgebucaran/fisher

**INSTALL FISHER**
```
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
```

**ADD PACKAGES**
```
fisher install <name>
```

```
fisher install ~/path/to/plugin
```

**LIST PACKAGES**
```
fisher list
```

**FISHER UPDATE**
```
fisher update jorgebucaran/fisher
```

**FISHER REMOVE PACKAGES**
```
fisher remove jorgebucaran/nvm.fish
```

**REMOVE FISHER**
```
fisher list | fisher remove
```

---

YOUTUBE: https://youtu.be/21ksdyl4x5Y
