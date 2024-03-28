**MY LINUX FOR WORK INSTALLATION OF HYPERLAND AND DOTFILES**

(this is setup for my direcotires so I can just copy paste EVERYTHING :) )


**INSTALL HYPERLAND ON ARCH**

git is required
```
sudo pacman -S git
```

Change into your GIT directory
```
cd ~/BIGDATA/git
```
```
git clone https://gitlab.com/stephan-raabe/hyprland-starter.git
```
```
cd hyprland-starter
```

Start the script
```
./install.sh
```



**INSTALL DOTFILES**

```
cd ~/BIGDATA/git/
```

```
git clone --depth=1 https://gitlab.com/stephan-raabe/dotfiles.git
```

```
./install.sh
```

**INSTALL DOTFILES WITH APPIMAGE**

(only if you don't want to install them via script)

Change to the download location (normally the Downloads folder)

```
cd ~/Downloads
```

Make the file executable
```
chmod +x ML4W_Dotfiles_Installer.AppImage
```

Start the App from your terminal with
```
./ML4W_Dotfiles_Installer.AppImage
```


**FOR MORE INFO GO TO:**


SOURCE DOTFILES: https://gitlab.com/stephan-raabe/dotfiles

SOURCE HYPERLAND: https://gitlab.com/stephan-raabe/hyprland-starter

There is much more explained on the above pages, so don't take this as guide, these are just my notes.

Everything belongs to Stephan Raabe.

YOUTUBE: https://www.youtube.com/watch?v=_j9Ww1kM-KU
