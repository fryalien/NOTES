**YOUTUBE:** https://youtu.be/QFxMZwfWG7g

---

Nix is functional programming language.

In flakes you define exactly which packages and channel you are using, so everybody has the same stuff.

---

**NIX FLAKES**

Add at the end of the config file:

```
micro /etc/nixos/configuration.nix
```

```
nix.settings.experimental-features = [ "nix-command" "flakes" ];
```

and then:

```
sudo nixos-rebuild switch
```

---

**LOCATION OF CONFIG FILES**

Once you have flakes enabled you can put your config files wherever you want with flakes.

For example put all in `nix` folder in the home folder.

```
mkdir ~/nix; cd ~/nix;
```

Copy all from /etc/nixos to nix folder.

```
cp /etc/nixos/configuration.nix ~/nix;
```

```
cp /etc/nixos/hardware-configuration.nix ~/nix;
```

Create `flake.nix` file.

```
micro flake.nix
```
Add the following text for unstable packages:

```
{

  description = "One flake to rule them all";

  inputs = {
    nixpkgs.url = "nixpkgs/nixos-unstable";
    };

  outputs = { self, nixpkgs, ... }:
  {  
    nixosConfigurations = {
      niki = nixpkgs.lib.nixosSystem {
        system = "x86_64-linux";
        modules = [ ./configuration.nix ];
        };
      };
   };

}
```

**When you have flakes you rebuild with:**

```
sudo nixos-rebuild switch --flake .
```

**Every time you update your system you update your flake file with:
(while inside your dotfiles directory).**

```
nix flake update
```
To actually update the system:

```
sudo nixos-rebuild switch --flake .
```

or to be sure (niki is the name of hostname in flake.nix file): 

```
sudo nixos-rebuild switch --flake ~/nix#niki
```

---

**GITHUB OF NIXOS CHANNELS**

https://github.com/NixOS/nixpkgs

---

**YOUTUBE:** https://youtu.be/QFxMZwfWG7g
