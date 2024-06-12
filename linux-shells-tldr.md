YOUTUBE: https://youtu.be/LYm7XlRcPmw

---

**SYSTEM SHELL**
```
ls -lh /bin/sh
```

```
ls -lh /usr/bin/sh
```

**INSTALL SHELLS**
```
sudo apt install fish zsh ksh dash tcsh csh
```

**DEFAULT USER SHELL**
```
echo $SHELL
```

> located in /etc/passwd
```
cat /etc/passwd
```

You can change that shell with (pick the shell you want):

```
chsh -s /usr/bin/fish
```

**ALL SHELLS CURRENTLY INSTALLED ON THE SYSTEM**
```
cat /etc/shells
```

**WHICH SHELL AM I CURRENTLY IN**
```
ps -p $$
```

OR for some shells

```
echo $0
```

**FISH SHELL**
```
ps -p %self
```

---

YOUTUBE: https://youtu.be/LYm7XlRcPmw
