# REPOS

| Distribution    | Repo config location                        |
| --------------- | ------------------------------------------- |
| **Fedora**      | `/etc/yum.repos.d/*.repo`                   |
| **Ubuntu**      | `/etc/apt/sources.list` + `sources.list.d/` |
| **Debian**      | `/etc/apt/sources.list` + `sources.list.d/` |
| **Arch Linux**  | `/etc/pacman.conf`                          |
| **CachyOS**     | `/etc/pacman.conf`                          |
| **EndeavourOS** | `/etc/pacman.conf`                          |

# MIRRORS

endos mirrors
/etc/pacman.d/mirrorlist
/etc/pacman.d/endeavouros-mirrorlist

cachy mirrors
/etc/pacman.d/mirrorlist
/etc/pacman.d/cachyos-mirrorlist

arch mirrors
/etc/pacman.d/mirrorlist

---

# RELEASES >> lsb_release -a

| Distribution    | Best command              |
| --------------- | ------------------------- |
| **Fedora**      | `cat /etc/fedora-release` |
| **Ubuntu**      | `cat /etc/os-release`     |
| **Debian**      | `cat /etc/debian_version` |
| **Arch Linux**  | `cat /etc/os-release`     |
| **CachyOS**     | `cat /etc/os-release`     |
| **EndeavourOS** | `cat /etc/os-release`     |

# mint specific
cat /etc/linuxmint/info

eos-release
cachyos-version

---

# KERNEL

uname -a
uname -r

cat /proc/version

---

# systemd distros
hostnamectl

---

# INIT SYSTEM

ps -p 1 -o comm=

ls -lh /sbin/init

systemctl is-system-running

---

# DISPLAY SERVER

echo $XDG_SESSION_TYPE

loginctl show-session $(loginctl | awk '/tty/ {print $1}') -p Type
