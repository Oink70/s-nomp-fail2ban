# z-nomp-fail2ban
fail2ban filters for s-nomp

/etc/fail2ban/jails.d, add to the current active *.conf file.

```sh
[s-nomp-InvalidBytes]
enabled = true
protocol = tcp
filter = s-nomp-InvalidBytes
logpath = /home/pool/.pm2/logs/pool-out.log
action   = iptables-allports[name=S-NOMP, protocol=all]
maxretry = 1
# 24 hours
bantime = 86400

[s-nomp]
enabled = true
protocol = tcp
filter = s-nomp
logpath = /home/pool/.pm2/logs/pool-out.log
action   = iptables-allports[name=S-NOMP, protocol=all]
maxretry = 10
# 1 hour
bantime = 3600
```

Put `s-nomp.conf` and `s-nomp-InvalidBytes.conf` in `/etc/fail2ban/filters.d`
