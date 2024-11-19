```
pg_lsclusters
pg_ctlcluster 12 main stop
pg_ctlcluster 13 main restart
pg_ctlcluster 14 main stop

pg_createcluster 13 c01 --port=5431
pg_dropcluster 13 c01
```
When creating the cluster with user like `pg_createcluster` -u `odoo` 13 `c02`    ,,, sometime you have to switch that user to start that cluster
Have to start auto or manual in `/etc/postgresql/version/cluster/start.conf`
```

psql -p 5433 -U postgres -d postgres 
CREATE USER odoo PASSWORD 'xxx';"
ALTER USER odoo PASSWORD 'yyy';"
CREATE ROLE apache WITH LOGIN SUPERUSER PASSWORD 'apache';
host    all             odoo              0.0.0.0/0           password

CREATE ROLE apache WITH LOGIN SUPERUSER PASSWORD 'apache';
```



After creating the clusters edit the `pg_hba in in /etc/postgresql/version/cluster` add the current user example. username
if different server listen_addresses = '*'    in `/etc/postgresql/version/cluster/posgres.conf`  or somewhat.conf  you know
restart the cluster