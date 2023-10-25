`sudo nano /etc/logrotate.d/rsyslog`

```
/var/log/syslog
{
    rotate 7
    daily
    maxsize 1G # add this line
    missingok
    notifempty
    delaycompress
    compress
    postrotate
        /usr/lib/rsyslog/rsyslog-rotate
    endscript
}
```


``` shell
echo "" > /var/log/kern.log
echo "" > /var/log/syslog
service syslog restart
journalctl --vacuum-size=50M
```

