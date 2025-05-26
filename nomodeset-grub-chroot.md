**Boot from live CD**

**Mount the root partition of your installed Linux Mint:**

```
sudo mount /dev/sdXn /mnt
```

>Replace /dev/sdXn with the appropriate device identifier for your root partition.


**Mount other necessary filesystems:**

```
sudo mount --bind /dev /mnt/dev
```

```
sudo mount --bind /proc /mnt/proc
```

```
sudo mount --bind /sys /mnt/sys
```

>Chroot into the mounted system:

```
sudo chroot /mnt
```

>Edit the GRUB configuration file:

```
sudo nano /etc/default/grub
```

>Find the line that starts with GRUB_CMDLINE_LINUX_DEFAULT and add nomodeset to it.

>For example: GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset"

>Update GRUB:

```
sudo update-grub
```

>Exit the chroot environment:

```
exit
```

>Unmount the filesystems:

```
sudo umount /mnt/dev
```

```
sudo umount /mnt/proc
```

```
sudo umount /mnt/sys
```

```
sudo umount /mnt
```

>Reboot your system:

```
sudo reboot
```

**In Arch Linux**

If you are using grub, add the parameter `nomodeset` into file `/etc/default/grub`, variable `GRUB_CMDLINE_LINUX_DEFAULT`.

```
micro /etc/default/grub
```

>Then run: 

```
sudo grub-mkconfig -o /boot/grub/grub.cfg
```