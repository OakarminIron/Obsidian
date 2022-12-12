[[Database Design]]

[[Database Languages]]

[[DBMS]]

[[ORM]]


Mysql While **a NULL itself does not require any storage space**, NDB reserves 4 bytes per row if the table definition contains any columns allowing NULL , up to 32 NULL columns. (If an NDB Cluster table is defined with more than 32 NULL columns up to 64 NULL columns, then 8 bytes per row are reserved.)

Postgresql Question: Does having `null` values take up a lot of Disk Space? Answer: No, Each `null` value only uses _one_ `bit` on disk.
https://github.com/dwyl/learn-postgresql/issues/49
