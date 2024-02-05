```bash
sudo nano /etc/systemd/system/odoo17c.service
```

```
[Unit]
Description=Odoo17c
Requires=postgresql.service
After=network.target postgresql.service
[Service]
Restart=always
RestartSec=3
Type=simple
SyslogIdentifier=odoo17c
PermissionsStartOnly=true
User=odoo
Group=odoo
ExecStart=/home/odoo/Documents/Projects/Odoo/venv17/bin/python3 /home/odoo/Documents/GitHub/odoo/odoo17c/odoo-bin -c /home/odoo/Documents/Projects/Odoo/Workspace/odoo17c.conf
StandardOutput=journal+console
[Install]
WantedBy=multi-user.target
```

``` bash
sudo systemctl daemon-reload
```