```
sudo -u postgres psql

ALTER DATABASE xxxxx REFRESH COLLATION VERSION;
ALTER DATABASE postgres REFRESH COLLATION VERSION;
```