```config
[options]

addons_path = /home/odoo/Documents/GitHub/odoo/odoo17c/addons , /home/odoo/Documents/GitHub/youraccount/yourrepo
csv_internal_sep = ,
data_dir = /home/odoo/.local/share/Odoo/17c
db_host = localhost
db_port = 5432
db_name = False
db_user = odoo
db_password = openpgpwd
db_maxconn = 8
db_sslmode = prefer
db_template = template0
demo = {'base': 1}
email_from = False
geoip_database = /usr/share/GeoIP/GeoLite2-City.mmdb
http_enable = True
http_interface =
http_port = 8069
import_partial =
limit_memory_hard = 3000000000
limit_memory_soft = 1000000000
max_cron_threads = 1
limit_request = 8192
limit_time_cpu = 600
limit_time_real = 1200
list_db = True
log_db = False
log_db_level = warning
log_handler = :INFO
log_level = debug
#logfile = /var/log/odoo/odoo17c.log
logrotate = True
longpolling_port = 8076
osv_memory_age_limit = 1.0
osv_memory_count_limit = False
pidfile = False
proxy_mode = False
reportgz = False
server_wide_modules = base,web
smtp_password = False
smtp_port = 25
smtp_server = localhost
smtp_ssl = False
smtp_user = False
syslog = False
test_enable = False
test_file = False
test_tags = None
translate_modules = ['all']
unaccent = False
without_demo = False
admin_passwd = $81T
```

[Documentation](https://www.odoo.com/documentation/17.0/administration/install/deploy.html#system-configuration)

And also check the limit_memory, `cron_thread`, and `db_maxcon`, because your server also have to carry weight of it's Operation System and PostgreSQL database.
It also depends on user type like `POS` Users can get many weight if they configure live inventory update.
Report viewers are also expensive. 

[Example Calcualtion](https://www.odoo.com/documentation/17.0/administration/install/deploy.html#id5)
[[Odoo Log]]