**NIXOS GENERAL**

>list active channel

```
sudo nix-channel --list
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

**WITH FALKES AND HOME MANAGER**

>update flake

```
cd ~/nix; nix flake update
```

>update the system

```
cd ~/nix; sudo nixos-rebuild switch --flake ~/nix
```

>update home-manager

```
cd ~/nix; home-manager switch --flake ~/nix
```

>rebuild home-manager

```
nix run home-manager/master -- switch -b backup --flake ~/nix
```

**WITHOUT FLAKES**

>update channel

```
sudo nix-channel --update
```

>update the system

```
sudo nixos-rebuild switch
```


**WITH FLAKES**

>update nix flake, has to be in the directory of the flake.lock file

```
cd ~/nix; nix flake update
```

>update the system

```
sudo nixos-rebuild switch --flake ~/nix
```
