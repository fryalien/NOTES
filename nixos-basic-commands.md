**NIXOS GENERAL**

>list active channel

```
sudo nix-channel --list
```

>switch to unstable channel

```
sudo nix-channel --add https://nixos.org/channels/nixos-unstable nixos
```

>delete old stuff

```
sudo nix-collect-garbage --delete-older-than 3d
```

>look when something is being delete

```
systemctl list-timers
```

>list generations

```
sudo nix-env --list-generations --profile /nix/var/nix/profiles/system
```

>nix info
```
nix-shell -p nix-info --run "nix-info -m"
```

>Build the configuration and make it the default boot option, but don't activate it until the next reboot

```
sudo nixos-rebuild boot
```

---

**WITHOUT FLAKES**

>update channel

```
sudo nix-channel --update
```

>update the system

```
sudo nixos-rebuild switch
```

>update all

```
sudo nixos-rebuild switch --upgrade
```

---

**WITH FLAKES**

>update nix flake, has to be in the directory of the flake.lock file

```
cd ~/nix; nix flake update
```

>update the system

```
sudo nixos-rebuild switch --flake ~/nix
```

---

**WITH FALKES AND HOME MANAGER**

>update flake

```
cd ~/nix; nix flake update
```

>update the system

```
cd ~/nix; sudo nixos-rebuild switch --flake ~/nix#niki
```

>update home-manager

```
cd ~/nix; home-manager switch --flake ~/nix#y
```

>rebuild home-manager

```
nix run home-manager/master -- switch -b backup --flake ~/nix#y
```
