**Put this in your `configuration.nix` file on your HOST machine.**

> `y` is the name of my user

```
{ config, pkgs, ... }:

{

  # Enable VirtualBox.
  virtualisation.virtualbox.host.enable = true;
  users.extraGroups.vboxusers.members = [ "y" ];

  # Extensions for VirtualBox
  virtualisation.virtualbox.host.enableExtensionPack = true;

}

```

**VirtualBox GUEST (`configuration.nix`)**

```
{
  # Enable VirtualBox guest
  virtualisation.virtualbox.guest.enable = true;
  virtualisation.virtualbox.guest.dragAndDrop = true;
  virtualisation.virtualbox.guest.seamless = true;
  virtualisation.virtualbox.guest.clipboard = true;
}
```
