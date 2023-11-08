[[Odoo Install Cloud]]

`sudo cat /etc/systemd/system/odoo16e.service`


```
[Unit]
Description=Odoo16e
Requires=postgresql.service
After=network.target postgresql.service
[Service]
Restart=always
RestartSec=3
Type=simple
SyslogIdentifier=odoo16e
PermissionsStartOnly=true
User=odoo
Group=odoo
ExecStart=/home/odoo/Documents/Projects/Odoo/venv16e/bin/python3 /home/odoo/Documents/Projects/Odoo/Workspace/odoo -c /home/odoo/Documents/Projects/Odoo/Workspace/odoo16e.conf
StandardOutput=journal+console
[Install]
WantedBy=multi-user.target
```

`sudo systemctl daemon-reload
`sudo systemctl start odoo16e`
`sudo systemctl enable odoo17e`