```bash
sudo nano /etc/systemd/system/odoo15.service
```

```
[Unit]
Description=Odoo15
Requires=postgresql.service
After=network.target postgresql.service
[Service]
Restart=always
RestartSec=3
Type=simple
SyslogIdentifier=odoo15
PermissionsStartOnly=true
User=odoo
Group=odoo
ExecStart=/home/odoo/Documents/Projects/Odoo/venv15/bin/python3 /home/odoo/Documents/GitHub/odoo/odoo15c/odoo-bin -c /home/odoo/Documents/Projects/Odoo/Workspace/odoo15.conf
StandardOutput=journal+console
[Install]
WantedBy=multi-user.target
```

``` bash
sudo systemctl daemon-reload
```