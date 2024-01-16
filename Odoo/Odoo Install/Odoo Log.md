In Linux first we create the folder
Set permission of that folder 
Create empty log file
Set permission of that file
```bash
sudo mkdir /var/log/odoo
sudo chown odoo:root /var/log/odoo
touch /var/log/odoo/odoo17c.log
chown odoo /var/log/odoo/odoo17e.log 
```


```in_odoo_config
logfile = /var/log/odoo/odoo17c.log
log_level = debug
logrotate = True
```

Log Levels
- debug is used for debugging.
- warning is used for showing the warnings.
- info is used for showing the information
- error is used for showing the errors.
- critical is used for showing the critical messages.

if you set debug and no rotate log will increase the storage with logs.