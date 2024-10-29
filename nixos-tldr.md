**YOUTUBE:** https://youtu.be/B_xvfxJqkOQ

---

**SWITCH TO NIXOS UNSTABLE**

List current channel.

```
sudo nix-channel --list
```

Switch to unstable.

```
sudo nix-channel --add https://nixos.org/channels/nixos-unstable nixos
```

```
sudo nixos-rebuild switch --upgrade
```

---

**INSTALL A PACKAGE**

**first add it to your configuration.nix file**

-- for only your user

packages = with pkgs; [
      package_name
    ];

-- system wide

environment.systemPackages = with pkgs; [
    package_name
    ];

```
sudo nixos-rebuild switch
```

---

**UPDATE PACKAGES**

**CHECK FOR UPDATES IN YOUR CHANNEL**

```
sudo nix-channel --update
```

**UPDATE PACKAGES**
```
sudo nixos-rebuild switch
```

---

**EVERYTIME YOU CHANGE confiuration.nix FILE RUN:**

```
sudo nixos-rebuild switch
```

---

**SETUP CLEAN INSTALLED PACKAGES**

```
sudo micro /etc/nixos/configuration.nix
```

Add the following lines at the end of the config file before }

```
# Automatic Garbage Collection
nix.gc = {
                automatic = true;
                dates = "weekly";
                options = "--delete-older-than 7d";
        };
```

---

**CHANGE SHELL FOR THE USER**

```
sudo micro /etc/nixos/configuration.nix
```

```
{ pkgs, ... }:

{
  ...

  programs.fish.enable = true;

  users.users.<myusername> = {
    ...
    shell = pkgs.fish;
    ...
  };
}
```

```
sudo nixos-rebuild switch
```

**IN KONSOLE CHANGE PATH**

```
/run/current-system/sw/bin/fish
```

---

**INSTALL A FIREWALL**

```
sudo micro /etc/nixos/configuration.nix
```

```
  # Warpinator and LocalSend
  networking.firewall.allowedTCPPorts = [ 42000 42001 53317 ];
  networking.firewall.allowedUDPPorts = [ 42000 42001 53317 ];
  networking.firewall.enable = true;
```

---

**LIST AND DELETE NIX TRASH**

```
nixos-rebuild list-generations
```

```
sudo nix-env --list-generations --profile /nix/var/nix/profiles/system
```

```
systemctl list-timers
```

```
sudo nix-collect-garbage --delete-older-than 5d
```

---

**Auto update:**

file:///nix/store/kj1sk97yphbm5ih8bwyghngzqba9nqjr-nixos-manual-html/share/doc/nixos/index.html#sec-changing-config

---

**Search for packages:**

https://search.nixos.org/

---

**YOUTUBE:** https://youtu.be/B_xvfxJqkOQ
