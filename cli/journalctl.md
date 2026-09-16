---
tags:
  - journalctl
  - cli
  - cli/journalctl
  - logs
---
> journalctl - Print log entries from the systemd journal

```shell
# --since & --until
journalctl --since today
journalctl --since yesterday

journalctl --since "5 minutes ago"
journalctl --since "30 min ago"
journalctl --since "2 hours ago"
journalctl --since "3 days ago"
journalctl --since "1 week ago"
journalctl --since "1 month ago"
journalctl --since "1 year ago"

journalctl --since "2026-07-10"
journalctl --since "2026-07-10 08:00"
journalctl --since "2026-07-10 14:30:15"

journalctl --since "30 minutes ago" --until "20 minutes ago"
journalctl --since "2026-01-01 00:00:00" --until "2026-01-02 00:00:00"

# reverse
journalctl --since today -r

# unit
journalctl -u cron.service

# follow
journalctl -f

# into file
journalctl --since today > log.txt
```
