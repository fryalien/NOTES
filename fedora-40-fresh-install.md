YOUTUBE: https://youtu.be/BRVFrEhecnY

---

**INSTALL MICRO**
```
sudo dnf install micro -y
```
**EDIT DNF CONFIG FILE**
```
micro /etc/dnf/dnf.conf
```

```

# ADDED BY ME
defaultyes=True
max_parallel_downloads=20
fastestmirror=True
countme=False
```

**UPDATE REPOSITORIES AND INSTALL UPDATES**
```
sudo dnf update --refresh
```

**INSTALL RPMFUSION FREE**
```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm -y
```

**INSTALL RPM-FUSION NON-FREE**
```
sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm -y
```

**INSTALL FOR GUI**
```
sudo dnf group update core -y
```

**INSTALL FLATPAK**
```
sudo dnf install flatpak -y
```

```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

**INSTALL CODECS ON FEDORA**
```
sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel -y
```

```
sudo dnf install lame\* --exclude=lame-deve -y
```

```
sudo dnf group upgrade --allowerasing --with-optional Multimedia -y
```

**INSTALL MEDIA PLAYERS**
```
sudo dnf install vlc mpv -y
```

**INSTALL FISH SHELL**
```
sudo dnf install fish -y
```

**CHANGE SHELL FOR CURRENT USER**
```
chsh -s /usr/bin/fish
```

**INSTALL GIT**
```
sudo dnf install git -y
```

**DOWNLOAD APPIMAGE LAUNCHER**

LINK: https://github.com/TheAssassin/AppImageLauncher/releases/

```
cd Downloads
```

```
wget https://github.com/TheAssassin/AppImageLauncher/releases/download/v2.2.0/appimagelauncher-2.2.0-travis995.0f91801.x86_64.rpm

```

```
sudo rpm -i appimagelauncher-2.2.0-travis995.0f91801.x86_64.rpm
```

**REMOVE FIREFOX / INSTALL LIBREWOLF**

```
sudo dnf remove firefox -y
```

> FLATPAK
```
flatpak install flathub io.gitlab.librewolf-community
```

> REPO INSTALL
```
curl -fsSL https://rpm.librewolf.net/librewolf-repo.repo | pkexec tee /etc/yum.repos.d/librewolf.repo
```

```
sudo dnf install librewolf -y
```
