Find Database Sizes
```sql
SELECT pg_size_pretty(pg_database_size('mydatabase'));
```

Find Size of Table

```sql
SELECT 
    t.table_name AS "Table_Name",
    pg_size_pretty(pg_relation_size(quote_ident(t.table_name))) AS "Table_Size",
    c.reltuples AS "RowCount"
FROM 
    information_schema.tables t
JOIN 
    pg_class c ON t.table_name = c.relname
JOIN 
    pg_namespace n ON c.relnamespace = n.oid
WHERE 
    t.table_schema = 'public' AND
    t.table_type = 'BASE TABLE' AND
    n.nspname = 'public'
ORDER BY 
    pg_relation_size(quote_ident(t.table_name)) DESC;

--------------------------------------------------
select table_schema, table_name, pg_relation_size('"'||table_schema||'"."'||table_name||'"')
from information_schema.tables
order by 3 desc;
--------------------------------------------------
SELECT
  schema_name,
  relname,
  pg_size_pretty(table_size) AS size
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


---------------- Find Useless Columns

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

Find Related Tables
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
xtable.table_name = 'account_account';  
```
------------------------------------------------------------------------------


Find F Key Counts
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

[[pgSQL Odoo]]
