

https://bytescout.com/blog/20-important-sql-queries.html
http://techslides.com/useful-sql-queries-and-commands

```sql
----------------------------------------------------
-- Find Table From All The Databases By Table Name
----------------------------------------------------
EXEC sys.sp_msforeachdb 'SELECT ''?'' DatabaseName, Name FROM [?].sys.Tables WHERE Name LIKE ''%Task_Schedule%'''

----------------------------------------------------
--Find Table By Column Name Using SQL Query
----------------------------------------------------
SELECT
    sys.tables.name AS 'Table Name', 
    sys.tables.object_id AS 'Object ID', 
    sys.columns.name AS 'Column Name'
FROM
    sys.tables INNER JOIN sys.columns 
        ON sys.tables.object_id = sys.columns.object_id
WHERE
    sys.columns.name LIKE '%RecCreatedBy%'
ORDER BY 1;

----------------------------------------------------
--Find Table By Table Name Querying Sys.Tables
----------------------------------------------------
SELECT * FROM sys.tables WHERE name LIKE     '%InHomeLNC%'
```
