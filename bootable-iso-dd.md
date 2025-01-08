Make a bootable ISO with `dd`.

```
sudo dd if=/path/to/filename.iso of=/dev/sdX bs=4M status=progress oflag=sync
```

Look for a disk.

```
sudo lsblk
```

LINK: https://pendrivelinux.com/create-bootable-usb-from-iso-using-dd/
