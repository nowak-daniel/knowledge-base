---
tags:
  - apt
  - history
  - upgrade
  - log
datum: 2026-07-30
---
Mit dem Befehl [[cli/apt|apt]] können die Pakete auf einem Debian System geupdatet werden.

# history.log

In `/var/log/apt/history.log*` wird die `apt` history gespeichert.
Der Inhalt wird in komprimierten gz-Dateien abgelegt, deswegen muss [[zgrep]] für die Suche verwendet werden.

```shell
ls -l /var/log/apt/history.log*
-rw-r--r-- 1 root root    0 Sep  1 00:53 /var/log/apt/history.log
-rw-r--r-- 1 root root  631 Aug 31 06:22 /var/log/apt/history.log.1.gz
-rw-r--r-- 1 root root 3098 Jul 31 06:18 /var/log/apt/history.log.2.gz

# liefert komplette history
sudo zgrep -hE '^(Start-Date|Commandline|Upgrade:|End-Date)' /var/log/apt/history.log*
```

## automatische updates

`/usr/bin/unattended-upgrade` führt automatisch updates aus.

```shell
sudo zgrep -A 6 -B 1 'Commandline: /usr/bin/unattended-upgrade' /var/log/apt/history.log*

Start-Date: 2026-07-22  06:52:57
Commandline: /usr/bin/unattended-upgrade
Remove: linux-image-6.12.86+deb13-amd64:amd64 (6.12.86-1)
End-Date: 2026-07-22  06:52:58
```
