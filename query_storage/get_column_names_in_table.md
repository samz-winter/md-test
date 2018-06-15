# Get Column Names in a Table
Use the following query to get all column names in a table.
```sql
select
  column_name, data_type
from
  information_schema.columns
where 
  table_schema = -- 'schema name' 
  and table_name = -- 'table name' 
order by 
  ordinal_position asc;  -- sorts in the order table displays
```
