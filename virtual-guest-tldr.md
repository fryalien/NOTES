**ARCH**

>Virtualbox guest

```
sudo pacman -S virtualbox-guest-utils
```

>QEMU

```
sudo pacman -S spice-vdagent qemu-guest-agent
```

Enable and start the service to ensure it runs at boot.

```
sudo systemctl enable --now qemu-guest-agent   
```

```
sudo systemctl enable --now spice-vdagentd
```

- spice-vdagent is what enables clipboard sharing
- qemu-guest-agent improves host↔guest integration (shutdown, IP reporting, etc.)
