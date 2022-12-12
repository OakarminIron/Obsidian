
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

------------------------------------------------------------------------------

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

---------------- find useless columns
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