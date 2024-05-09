Reverse Find
```SQL
SELECT code_list.code
FROM (
    SELECT unnest(ARRAY[700001, 700002, 700003, 700004, 700005, 700006, 700007]) AS code
) AS code_list
LEFT JOIN account_account ON code_list.code = account_account.code::integer
WHERE account_account.code IS NULL;

SELECT name_list.name FROM ( SELECT unnest(ARRAY['Name1', 'Name2', 'Name3', 'Name4']) AS name ) AS name_list LEFT JOIN account_account ON name_list.name = account_account.name WHERE account_account.name IS NULL;

SELECT name_list.name FROM ( SELECT unnest(ARRAY['Name1', 'Name2', 'Name3', 'Name4']) AS name ) AS name_list LEFT JOIN account_account ON name_list.name = (account_account.name->>'en_US')::text WHERE account_account.name IS NULL;
```

```SQL
select id from ir_ui_view where (arch_db->>'en_US')::text like '%LLLLLLL%'
```

in Odoo but not in PG
```sql
SELECT field_description.name AS field_name
FROM (
    SELECT name
    FROM ir_model_fields
    WHERE model = 'res.partner'
) AS field_description
LEFT JOIN (
    SELECT column_name
    FROM information_schema.columns
    WHERE table_name = 'res_partner'
) AS db_fields ON field_description.name = db_fields.column_name
WHERE db_fields.column_name IS NULL;

```


``` SQL
WITH DuplicateAccounts AS (
    SELECT  id,  name, ROW_NUMBER() OVER (PARTITION BY name ORDER BY id) AS rn
    FROM 
        account_account
    WHERE 
        name IN (SELECT name FROM account_account GROUP BY name HAVING COUNT(name) > 1)
)
UPDATE 
    account_account
SET 
    name = 'z' || DuplicateAccounts.name
FROM 
    DuplicateAccounts
WHERE 
    account_account.id = DuplicateAccounts.id
    AND DuplicateAccounts.rn > 1;
```

invoice by year
```sql
SELECT
    EXTRACT(YEAR FROM create_date) AS year,
    SUM(amount_total) AS total_amount
FROM account_move
WHERE state = 'paid'
GROUP BY EXTRACT(YEAR FROM create_date)
ORDER BY year;

```