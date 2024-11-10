**Put this in your `configuration.nix` file on your HOST machine.**

```
{ config, pkgs, ... }:

{

  virtualisation.libvirtd.enable = true;
  programs.virt-manager.enable = true;

}

```

**Virt-manager GUEST (`configuration.nix`)**

```
{
  services.qemuGuest.enable = true;
  services.spice-vdagentd.enable = true;  # enable copy and paste between host and guest
}
```

**Check the status of the default network on Virt-Manager**

```
sudo virsh net-list --all
```

**Autostart default network**

```
sudo virsh net-autostart --network default
```

**Put your user in `libvirtd` group (`configuration.nix`)**

```
users.users.y = {
	...
	...
	extraGroups = [ "networkmanager" "wheel" "libvirtd" ];
	...
}
```
