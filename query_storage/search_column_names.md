# Search Column Names

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

> ***NOTE:***\
> 💀 This is a query that is for querying things

```sql
SELECT
date(date) as month,
ticket_form_name,
primary_contact,
secondary_contact,
source1,
(case when email like '%nex.%' then 'Nexrep' 
when email like '%tp.%' then 'Teleperformance' 
when email like '%ly.%' then 'Startek' 
when email like '%cos.%' then 'Startek' 
when email like '%fs.%' then 'Fusion' 
else 'Chicago' end) as partner_group,
count(b.ticket_id) as total_contacts,
avg(aht_simple) as average_handle_time,
avg(aht_simple) * count(b.ticket_id) as total_handle_time
from
(SELECT distinct
t.created_time_central as date,
t.ticket_id,
tf.name as ticket_form_name,
c.name as primary_contact,
cr.name as secondary_contact,
case when t.gh_source_channel_id in (28,29,30,31) then 'calls'
when t.gh_source_channel_id = 36 then 'chats'
when metrics_urgent = 1 then 'urgent ticket'
when metrics_less_urgent = 1 then 'urgent ticket'
else 'other' end as source1,
case when (datediff('second',t.assigned_time_central,t.resolved_time_central)> 0 
and datediff('second',t.assigned_time_central,t.resolved_time_central)<=2400) then
datediff('second',t.assigned_time_central,t.resolved_time_central) else null end as aht_simple,
a.email
from zendesk.ticket t
left join zendesk.assignee a on t.assignee_id = a.assignee_id
left join zendesk.grubhub_source_channel g on t.gh_source_channel_id = g.gh_source_channel_id
left join zendesk.contact_reason c on t.primary_contact_reason = c.contact_reason_id
left join zendesk.contact_reason cr on t.secondary_contact_reason = cr.contact_reason_id
left join zendesk.ticket_forms tf on t.ticket_form_id = tf.ticket_form_id
where t.gh_source_channel_id not in (38,51)
and t.ticket_form_id in (107903,141143,141163,175086)
and t.created_time_central > '2018-01-01'
group by 1,2,3,4,5,6,7,8
)b
group by 1,2,3,4,5,6
order by 1,2,3,4,5,6
```
