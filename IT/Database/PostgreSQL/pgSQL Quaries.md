Find Related Table
```sql
SELECT xtable.table_name AS xtable,
       kcu.column_name AS xcolumns,
       allforeignkey.table_name AS ref_table,
       allforeignkey.column_name AS ref_column    
FROM  information_schema.table_constraints AS xtable
JOIN (    
  SELECT table_name,
         column_name,
         unique_constraint_name
  FROM information_schema.referential_constraints    
  INNER JOIN information_schema.key_column_usage AS kcu
  ON information_schema.referential_constraints.constraint_name = kcu.constraint_name    
) AS allforeignkey
ON xtable.constraint_name = allforeignkey.unique_constraint_name    
INNER JOIN information_schema.key_column_usage AS kcu
ON xtable.constraint_name = kcu.constraint_name    
WHERE 
xtable.table_name = 'account_asset_asset';  
```
------------------------------------------------------------------------------

find database size
```sql
SELECT pg_size_pretty(pg_database_size('mydatabase'));
```
---------------- find useless columns

```sql
select nspname, relname, attname, typname,
    (stanullfrac*100)::int as null_percent,
    case when stadistinct >= 0 then stadistinct else abs(stadistinct)*reltuples end as "distinct",
    case 1 when stakind1 then stavalues1 when stakind2 then stavalues2 end as "values"
from pg_class c
join pg_namespace ns on (ns.oid=relnamespace)
join pg_attribute on (c.oid=attrelid)
join pg_type t on (t.oid=atttypid)
join pg_statistic on (c.oid=starelid and staattnum=attnum)
where nspname not like E'pg\\_%' and nspname != 'information_schema'
  and relkind='r' and not attisdropped and attstattarget != 0
  and reltuples >= 100              -- ignore tables with fewer than 100 rows
  and stadistinct between 0 and 4   -- 0 to 1 distinct values
  and attname not in ('company_id','create_uid','write_uid','currency_id' )
order by 6,5,2
;
```

Find Size in Table

```sql
select
  table_name,
  pg_size_pretty(pg_relation_size(quote_ident(table_name))),
  pg_relation_size(quote_ident(table_name))
from information_schema.tables
where table_schema = 'public'
order by 3 desc;
```

```sql
select table_schema, table_name, pg_relation_size('"'||table_schema||'"."'||table_name||'"')
from information_schema.tables
order by 3
```

```sql
SELECT
  schema_name,
  relname,
  pg_size_pretty(table_size) AS size,
  table_size

FROM (
       SELECT
         pg_catalog.pg_namespace.nspname           AS schema_name,
         relname,
         pg_relation_size(pg_catalog.pg_class.oid) AS table_size

       FROM pg_catalog.pg_class
         JOIN pg_catalog.pg_namespace ON relnamespace = pg_catalog.pg_namespace.oid
     ) t
WHERE schema_name NOT LIKE 'pg_%'
ORDER BY table_size DESC;
```



----- ???

```sql

SELECT xtable.table_name AS xtable, count(xtable.table_name) as x
FROM  information_schema.table_constraints AS xtable
JOIN (    
  SELECT table_name,
         column_name,
         unique_constraint_name
  FROM information_schema.referential_constraints    
  INNER JOIN information_schema.key_column_usage AS kcu
  ON information_schema.referential_constraints.constraint_name = kcu.constraint_name    
) AS allforeignkey
ON xtable.constraint_name = allforeignkey.unique_constraint_name    
INNER JOIN information_schema.key_column_usage AS kcu
ON xtable.constraint_name = kcu.constraint_name    
group by 1 order by 2 desc
```


Reverse Find
```SQL
SELECT code_list.code
FROM (
    SELECT unnest(ARRAY[700001, 700002, 700003, 700004, 700005, 700006, 700007]) AS code
) AS code_list
LEFT JOIN account_account ON code_list.code = account_account.code::integer
WHERE account_account.code IS NULL;
```