[[Horizontal Partitioning]] (_**sharding_**_)_ stores rows of a table in multiple database clusters.

[[Vertical Partitioning]] stores tables &/or columns in a separate database or tables.

1.  Each database server must be the same structurally.
2.  Data records are sensibly divided in a sharded DB.
3.  Each data record exists in only one shard (other than audit tables/backups)

https://www.scalingpostgres.com/
https://www.youtube.com/@ScalingPostgres