**fstrim - discard (trim) unused blocks on a mounted filesystem, best used on SSD and NVMe drives**

**Avoid it on HDD! It can cause errors or data corruption.**

>Enable timer.

```
sudo systemctl enable --now fstrim.timer
```

>Start timer.

```
sudo systemctl start fstrim.timer
```

>Check status.

```
sudo systemctl status fstrim.timer
```

>Check if the drive supports it.

```
sudo lsblk --discard   
```

Look for non-zero values in the DISC-GRAN and DISC-MAX columns. If present, TRIM is supported.
