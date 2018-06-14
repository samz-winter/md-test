# Markdown Folder and Document Test

> ***NOTE:***\
> Don't forget, you can add blockquotes to make information stand out!\

Use the following query to search all column names in a schema.
```sql
select
  table_schema, table_name, column_name, data_type
from
  information_schema.columns
where 
  column_name like '%cust%'
order by 
  1,2,ordinal_position asc
```

Use the following query to get all column names in a table.
```sql
select
  column_name, data_type
from
  information_schema.columns
where 
  table_schema = 'restaurant_reporting' -- schema name 
  and table_name = 'gfr_restaurant_totals' -- table name 
order by 
  ordinal_position asc;  -- sorts in the order table displays
```
