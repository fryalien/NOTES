**OPEN MANDRIVA & DNF**
```
alias u="sudo dnf dsync --refresh"
alias dar="sudo dnf autoremove"
alias i="sudo dnf install"
alias pkr="sudo dnf remove"
alias pks="sudo dnf search"

alias omcl="sudo dnf clean all ; dnf clean all ; dnf repolist"
alas omu="sudo dnf --allowerasing distro-sync"
```

**DNF**
```
# ADDED BY ME
defaultyes=True
max_parallel_downloads=20
fastestmirror=True
countme=False
```

**PACMAN**
```
alias u="sudo pacman -Syu"
alias i="sudo pacman -S"
alias pkr="sudo pacman -Rs"
alias pks="sudo pacman -Ss"
alias yi="yay -S"
alias pi="paru -S"
alias upall="yay -Syu"
```

**APT**
```
alias u="sudo apt update && sudo apt upgrade"
alias i="sudo apt install"
alias pkr="sudo apt remove"
alias pks="sudo apt search"
```

**ZYPPER**
```
alias u="sudo zypper update"
alias i="sudo zypper install"
alias pkr="sudo zypper remove"
alias pks="sudo zypper search"
```

**FLATPAK**
```
abbr f="flatpak install"
abbr fu="flatpak update"
abbr fr="flatpak remove"
abbr fs="flatpak search"
abbr fcl="flatpak uninstall --unused"
abbr fls="flatpak list"
```
