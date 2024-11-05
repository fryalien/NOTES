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

>UPDATE FLAKE

```
cd ~/nix; nix flake update
```

**UPDATE SYSTEM**

```
cd ~/nix; sudo nixos-rebuild switch --flake ~/nix
```

>UPDATE HOME-MANAGER

```
cd ~/nix; home-manager switch --flake ~/nix
```

>REBUILD HOME-MANAGER

```
nix run home-manager/master -- switch -b backup --flake ~/nix
```

**WITHOUT FLAKES**

>UPDATE CHANNEL

```
sudo nix-channel --update
```

>UPDATE SYSTEM

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
