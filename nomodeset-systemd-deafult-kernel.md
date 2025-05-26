**systemd-boot default kernel**

>switch to root

```
su -
```

```
bootctl set-default choose_your_kernel
```

**nomodeset**

>write under options in

`/boot/loader/entries/choose_your_kernel.conf`

```
nomodeset
```

**to make nomodeset permanent add it to this file**

```
micro /etc/kernel/cmdline
```