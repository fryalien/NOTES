**Put this in your configuration.nix file on your host machine.**

```
{ config, pkgs, ... }:

{

  virtualisation.libvirtd.enable = true;
  programs.virt-manager.enable = true;

}

```

**Virt-manager GUEST (configuration.nix)**

```
{
  services.qemuGuest.enable = true;
  services.spice-vdagentd.enable = true;  # enable copy and paste between host and guest
}
```

**CHECK STATUS OF DEFAULT NETWORK ON VIRT-MANAGER**

```
sudo virsh net-list --all
```

**AUTOSTART DEFAULT NETWORK**

```
sudo virsh net-autostart --network default
```
