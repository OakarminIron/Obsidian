```bash
sudo apt update
sudo apt install nginx certbot python3-certbot-nginx
sudo nano /etc/nginx/sites-available/odoo
```

``` config
server {
    listen 80;
    client_max_body_size 500M;
    server_name xxx.com;
    location / {
        proxy_pass http://localhost:8069;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

server {
    listen 443 ssl;
    server_name xxx.com;
    client_max_body_size 500M;
    ssl_certificate /etc/letsencrypt/live/xxx.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/xxx.com/privkey.pem;
    include /etc/letsencrypt/options-ssl-nginx.conf;
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem;
    location / {
        proxy_pass http://localhost:8069;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_read_timeout 86400;
    }
}

===========================================================================after


server {
    client_max_body_size 5000M;
    server_name xxx.com;
    location / {
        proxy_pass http://localhost:8069;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
    listen 443 ssl; # managed by Certbot
    ssl_certificate /etc/letsencrypt/live/xxx.com/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/xxx.com/privkey.pem; # managed by Certbot
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot

}
server {
    if ($host = xxx.com) {
        return 301 https://$host$request_uri;
    } # managed by Certbot
    listen 80;
    server_name xxx.com;
    return 404; # managed by Certbot

}







```

```bash
sudo ln -s /etc/nginx/sites-available/odoo /etc/nginx/sites-enabled/
sudo certbot --nginx -d xxx.com
sudo nginx -t
sudo systemctl restart nginx
```

check firewall