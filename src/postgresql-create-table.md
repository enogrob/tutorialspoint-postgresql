**PostgreSQL - CREATE Table**

The PostgreSQL CREATE TABLE statement is used to create a new table in any of the given database.

Syntax
Basic syntax of CREATE TABLE statement is as follows:
```sql
CREATE TABLE table_name(
   column1 datatype,
   column2 datatype,
   column3 datatype,
   .....
   columnN datatype,
   PRIMARY KEY( one or more columns )
);
```

CREATE TABLE is the keyword telling the database system to create a new table. The unique name or identifier for the table follows the CREATE TABLE statement. Initially empty table in the current database and will be owned by the user issuing the command.

Then in brackets comes the list defining each column in the table and what sort of data type it is. The syntax becomes clearer with an example below.

Examples
Following is an example, which creates a COMPANY table with ID as primary key and NOT NULL are the constraints showing that these fields can not be NULL while creating records in this table:
```bash
createdb testdb
psql
\c testdb
```

```sql
CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL
);
```

Let us create one more table, which we will use in our exercises in subsequent chapters:
```sql
CREATE TABLE DEPARTMENT(
   ID INT PRIMARY KEY      NOT NULL,
   DEPT           CHAR(50) NOT NULL,
   EMP_ID         INT      NOT NULL
);
```

You can verify if your table has been created successfully using \d command, which will be used to list down all the tables in an attached database.
```
testdb-# \d
Above PostgreSQL statement will produce the following result:

           List of relations
 Schema |    Name    | Type  |  Owner
--------+------------+-------+----------
 public | company    | table | postgres
 public | department | table | postgres
(2 rows)
```

Use \d tablename to describe each table as shown below:
```
testdb-# \d company
Above PostgreSQL statement will produce the following result:

        Table "public.company"
  Column   |     Type      | Modifiers
-----------+---------------+-----------
 id        | integer       | not null
 name      | text          | not null
 age       | integer       | not null
 address   | character(50) |
 salary    | real          |
 join_date | date          |
Indexes:
    "company_pkey" PRIMARY KEY, btree (id)
```
