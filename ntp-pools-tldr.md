**CHANGE NTP on Arch**

```
micro /etc/systemd/timesyncd.conf
```

>Change this

```
[Time]
NTP=0.de.pool.ntp.org 1.de.pool.ntp.org 2.de.pool.ntp.org 3.de.pool.ntp.org 
FallbackNTP=europe.pool.ntp.org
```

>Restart

```
sudo systemctl restart systemd-timesyncd
```

>Check

```
timedatectl timesync-status
```


DEFAULT
#NTP=
#FallbackNTP=0.arch.pool.ntp.org 1.arch.pool.ntp.org 2.arch.pool.ntp.org 3.arch.pool.ntp.org

