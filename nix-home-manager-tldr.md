**YOUTUBE:** https://youtu.be/QFxMZwfWG7g

---

**HOME-MANAGER SETUP**

**INSTALLING STANDALONE**
- manged by user accounts
- system and user configurations are separated

https://nix-community.github.io/home-manager/index.xhtml#sec-install-standalone

```
nix-channel --add https://github.com/nix-community/home-manager/archive/master.tar.gz home-manager
```

```
nix-channel --update
```

```
nix-shell '<home-manager>' -A install
```

**if you get error like home manager source not found, or whatever, just logout and run install again**

If it's installed properly it will say staring home manaer activation...

It will crate a file `home.nix`

---

**REBUILD SYSTEM WITH HOME MANAGER (rebuild switch in nixos)**

```
home-manager switch
```

copy `home.nix` to you dofiles directory

```
cp ~./config/home-manager/home.nix ~/nix
```

**ADD HOME-MANAGER TO YOUR FLAKE FILE**

>At `flake.nix` config file add:

```
{

  description = "One flake to rule them all";

  inputs = {
    nixpkgs.url = "nixpkgs/nixos-unstable";
    home-manager.url = "github:nix-community/home-manager/master";
    home-manager.inputs.nixpkgs.follows = "nixpkgs";
  };

  outputs = { self, nixpkgs, home-manager, ... }:
    {
      nixosConfigurations = {
        niki = nixpkgs.lib.nixosSystem {
          system = "x86_64-linux";
          modules = [ ./configuration.nix ];
        };
      };

      homeConfigurations = {
        y = home-manager.lib.homeManagerConfiguration {
          pkgs = nixpkgs.legacyPackages."x86_64-linux";
          modules = [ ./home.nix ];
        };
      };
    };

}
```

**AFTER EDITING RUN in config dir:** (all config files shoud have user permission)

```
cd ~/nix; home-manager switch --flake .
```

---

**LET HOME MANAGER MANAGES ITSELF**

Add this to `home.nix` file"

```
programs.home-manager.enable = true;
```

---

**ADD CONFIG FILES TO YOUR HOME MANAGER**

```
home.file."path-to-actual-file".source = .path-to-actual-config-file;
```

For example:

```
home.file."~/.config/fish/config.fish".source = ./system/config.fish;
```

or import the whole directory:

```
home.file.".config/somedirectory".source = ./somedirectory;
```

**RUN THIS WHEN INITIALIZING FOLDERS FOR THE FIRST TIME**

```
nix run home-manager/master -- switch -b backup --flake .
```

or to be sure

```
nix run home-manager/master -- switch -b backup --flake ~/nix#y
```

---

**RESTORE HOME-MANAGER CONFIGURATION**

To list home manager generations:

```
home-manager generations
```

You will get a list like this:

```
2024-10-22 15:53 : id 2 -> /nix/store/3j2g8vj20dlcgp1y01mwwy44jf3ymiz8-home-manager-generation
2024-10-22 14:59 : id 1 -> /nix/store/jqd1ddlvf71274xbpf2d4zp68gi208x9-home-manager-generation
```

To activate a specific generation add `/activate` at the end of generation link:

```
/nix/store/jqd1ddlvf71274xbpf2d4zp68gi208x9-home-manager-generation/activate
```

Than just switch (in `~/nix` folder):

```
home-manager switch --flake .
```

or to be sure

```
home-manager switch --flake ~/nix#y
```

---

**YOUTUBE:** https://youtu.be/QFxMZwfWG7g
