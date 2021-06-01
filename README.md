# oracle-sql-database-structure-explorer  
Code snippets to find constraints and table relationships in an Oracle database.  

## Make the current session case-insensitive
```
-- make the current session case-insensitive (in case your tables or columns have FancyNamesLikeThis)
alter session set nls_sort=BINARY_CI;
alter session set nls_comp=LINGUISTIC;
```

## List all tables in the database accessible by the current user  
```
-- list all tables in the database accessible by the current user
SELECT
       owner
     , table_name
     , num_rows
FROM
       all_tables
;

```  

## List all tables that contain a column with an specific name   
```
-- list all tables that contain a column with name
SELECT
       table_name
     , column_name
     , data_type
     , nullable
FROM
       all_tab_columns
WHERE
       column_name = 'PICK_COLUMN'
;
```

## List all primary keys  
```
-- select all primary keys
SELECT
         all_constraints.constraint_type
       , all_cons_columns.table_name
       , all_cons_columns.column_name
       , all_constraints.constraint_name
       , all_cons_columns.position
       , all_constraints.status
       , all_cons_columns.owner as schema_name
FROM
         all_constraints
         JOIN
                  all_cons_columns
                  ON
                           all_constraints.constraint_name = all_cons_columns.constraint_name
                           and all_constraints.owner       = all_cons_columns.owner
WHERE
         all_constraints.constraint_type = 'P'
ORDER BY
         all_cons_columns.owner
       , all_cons_columns.table_name
       , all_cons_columns.position
;
```


## List all tables with a relationship  

```
-- select related tables
SELECT
       p.table_name
     , c.column_name
     , 'Select count(*) from '
              || F.table_name
              || ' where '
              || c.column_name
              || ' = ' strSql
FROM
       user_constraints  P
     , user_constraints  F
     , user_cons_columns c
WHERE
       P.constraint_name     = F.r_constraint_name
       AND f.constraint_name = C.constraint_name
       AND F.table_name      = C.table_name
       AND p.table_name IN UPPER(('TABLE_NAME_GOES_HERE'))
;
```


## List all schema objects

```
-- list Schema Objects
SELECT 
  object_type
  , object_name 
  , status  
FROM user_objects
ORDER BY 
  object_type
  , object_name
;
```

## Generate insert script from table structure  

``` 
-- generate insert script
SELECT 
	'insert into (' ||
	user_tab_columns.table_name ||
	LISTAGG(column_name, ', ') WITHIN GROUP (ORDER BY column_name ) ||
	') values (' ||
	LISTAGG(nullable || '_' || data_type, ', ') WITHIN GROUP (ORDER BY column_name ) ||
	');' as insert_command
FROM user_tab_columns
WHERE table_name = upper('TABLE_NAME_GOES_HERE')
GROUP BY table_name;
```   

