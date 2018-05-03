# Find on DBA Source

You can use this command to find specific lines or text in DBA_SOURCE (PROCEDURES, FUNCTIONS, PACKAGES).

```sql
select
  * 
FROM 
  DBA_SOURCE
WHERE 
  UPPER(TEXT) LIKE '%TEXT YOU ARE LOOKING FOR%'
AND 
  OWNER LIKE '%Owner of the object%'
AND
  TYPE IN  (Types that you are looking for);

```

### Example

```sql
select
  * 
FROM 
  DBA_SOURCE
WHERE 
  UPPER(TEXT) LIKE '%IMPORT%'
AND 
  OWNER LIKE '%OWNER%'
AND
  TYPE IN  ('PROCEDURE','FUNCTION','PACKAGE BODY');
```
