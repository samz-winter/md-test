# Testing full Markdown usage

> **NOTE:**
> • This is just a test of some Markdown in a document
> • Markdown can be used as long as the file type is .md


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
