# INSTALL QEMU/KVM ON ARCH
```
sudo pacman -S qemu-full virt-manager virt-viewer dnsmasq bridge-utils libguestfs ebtables vde2 openbsd-netcat
```

> UNCOMMENT THIS VALUES**
```
sudo micro /etc/libvirt/libvirtd.conf
```

unix_sock_group = "libvirt"

unix_sock_rw_perms = "0777"

**ADD USER TO libvirt GROUP**
```
sudo usermod -aG libvirt $USER
```

**ENABLE SERVICE**
```
systemctl enable libvirtd.service
```

**START SERVICE**
```
systemctl start libvirtd.service
```

> CHECK THE STATUS
```
systemctl status libvirtd.service
```

> START THE APPLICATION

SOURCE: https://linuxways.net/arch/install-kvm-arch-linux/

# INSTALL QEMU/KVM ON FEDORA

> CHECK IF VIRTUALIZATION EXISTS
```
lscpu | grep Virtualization
```

AMD:
Virtualization:                     AMD-V
INTEL
Virtualization:                     VT-x

```
sudo dnf install qemu-kvm libvirt virt-install bridge-utils virt-manager libvirt-devel virt-top libguestfs-tools guestfs-tools
```
```
sudo systemctl start libvirtd
```
```
sudo systemctl enable libvirtd
```
```
sudo systemctl status libvirtd
```
```
sudo micro /etc/libvirt/libvirtd.conf
```
> UNCOMMENT THIS VALUES**
```
sudo micro /etc/libvirt/libvirtd.conf
```

unix_sock_group = "libvirt"

unix_sock_rw_perms = "0777"

```
sudo usermod -a -G libvirt $(whoami)
```
```
sudo systemctl start libvirtd
```
```
sudo systemctl enable libvirtd
```
```
systemctl status libvirtd
```






### TLDR
KVM and QEMU are two different virtualization technologies, one has a type 1 hypervisor and the other has a type 2 hypervisor. KVM runs directly on hardware, whereas QEMU runs on top of the operating system. QEMU uses KVM as a backend to access hardware resources and use the software emulation to visualize the hardware.
