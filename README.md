# z-nomp-fail2ban
fail2ban filters for z-nomp

/etc/fail2ban/jails.d, add to the current active *.conf file.

```sh
[s-nomp]
enabled = true
protocol = tcp
filter = s-nomp
logpath = /home/pool/.pm2/logs/pool-out.log
action   = iptables-allports[name=S-NOMP, protocol=all] 
maxretry = 30
# 1 hour
bantime = 3600
```

Put s-nomp.conf in /etc/fail2ban/filters.d
