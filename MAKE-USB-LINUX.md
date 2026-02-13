Identify the USB Device:

Insert your USB drive and use the `lsblk` or `sudo fdisk -l` command to identify its device name (e.g., /dev/sdb, /dev/sdc).

Ensure you correctly identify the device to avoid overwriting the wrong drive.

Unmount the USB Drive: Before writing, unmount any partitions on the USB drive using the umount command (e.g., `sudo umount /dev/sdX1`) to prevent data corruption.


sudo dd bs=4M if=/path/to/your-file.iso of=/dev/sdX status=progress oflag=sync

`sudo dd bs=4M if=/home/y/BIGDATA/ISO/your-file.iso of=/dev/sdX status=progress oflag=sync`
