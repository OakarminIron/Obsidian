[[Database Engineering]]
[[Database Design]]
[[Query Languages]]
[[Database Type]]
[[ORM (Object-Relational Mapping)]]


MySQL While , NDB reserves 4 bytes per row if the table definition contains any columns allowing NULL , up to 32 NULL columns. (If an NDB Cluster table is defined with more than 32 NULL columns up to 64 NULL columns, then 8 bytes per row are reserved.)

PostgreSQL Question: Does having `null` values take up a lot of Disk Space? Answer: No, Each `null` value only uses _one_ `bit` on disk.
https://github.com/dwyl/learn-postgresql/issues/49
