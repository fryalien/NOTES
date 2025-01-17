YOUTUBE: https://youtu.be/YWscSDQ_ikY

---

**OPENMANDRIVA ROME**

Homepage: https://www.openmandriva.org/

Forum: https://forum.openmandriva.org/

Wiki: https://wiki.openmandriva.org/en/home

---

**CONFIGURE DNF**

```
sudo vi /etc/dnf/dnf.conf
```

```
# ADDED BY ME
defaultyes=True
max_parallel_downloads=20
fastestmirror=True
countme=False
```

**UPGRADE ROME RELEASE (from their wiki)**

```
sudo dnf clean all ; dnf clean all ; dnf repolist
```

```
sudo dnf --allowerasing distro-sync
```

**INSTALL PLASMA X11**

```
sudo dnf install task-plasma6-X11
```

**INSTALL PLASMA WAYLAND**

```
sudo dnf install plasma6-workspace-wayland plasma6-kwin-wayland plasma6-libkscreen-wayland kf6-kidletime-wayland kf6-kwindowsystem-backend-wayland
```

**INSTALL ANY DE**

```
sudo dnf install task-cosimc
```

**LIST REPOSITORIES**

```
dnf repolist
```

**INSTALL A PACKAGE**

```
sudo dnf install micro
```

**REMOVE A PACKAGE**

```
sudo dnf remove micro
```

**SEARCH FOR A PACKAGE**

```
sudo dnf search micro
```

**CLEAN UP SYSTEM**

```
sudo dnf -y autoremove; dnf clean all
```

---

YOUTUBE: https://youtu.be/YWscSDQ_ikY
