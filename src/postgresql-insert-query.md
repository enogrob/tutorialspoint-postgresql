**PostgreSQL - INSERT Query**

The PostgreSQL INSERT INTO statement allows one to insert new rows into a table. One can insert a single row at a time or several rows as a result of a query.

Syntax
Basic syntax of INSERT INTO statement is as follows.
```
INSERT INTO TABLE_NAME (column1, column2, column3,...columnN)
VALUES (value1, value2, value3,...valueN);
```

Here, column1, column2,...columnN are the names of the columns in the table into which you want to insert data.

The target column names can be listed in any order. The values supplied by the VALUES clause or query are associated with the explicit or implicit column list left-to-right.

You may not need to specify the column(s) name in the SQL query if you are adding values for all the columns of the table. But make sure the order of the values is in the same order as the columns in the table. The SQL INSERT INTO syntax would be as follows:
```
INSERT INTO TABLE_NAME VALUES (value1,value2,value3,...valueN);
```

Output

The following table summarizes the output messages and their meaning:

Output Message	Description
```
INSERT oid 1	Message returned if only one row was inserted. oid is the numeric OID of the inserted row.
INSERT 0 #	Message returned if more than one rows were inserted. # is the number of rows inserted.
```

Examples
Let us create COMPANY table in testdb as follows:
```
\c testdb
\d
```

```sql
CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL,
   JOIN_DATE	  DATE
);
```

Following example inserts a row into the COMPANY table:
```sql
INSERT INTO COMPANY (ID,NAME,AGE,ADDRESS,SALARY,JOIN_DATE) VALUES (1, 'Paul', 32, 'California', 20000.00 ,'2001-07-13');
```

Following example is to insert a row; here salary column is omitted and therefore it will have the default value:
```sql
INSERT INTO COMPANY (ID,NAME,AGE,ADDRESS,JOIN_DATE) VALUES (2, 'Allen', 25, 'Texas', '2007-12-13');
```

Following example uses the DEFAULT clause for the ADDRESS columns rather than specifying a value:
```sql
INSERT INTO COMPANY (ID,NAME,AGE,ADDRESS,SALARY,JOIN_DATE) VALUES (3, 'Teddy', 23, 'Norway', 20000.00, DEFAULT );
```

Following example inserts multiple rows using the multirow VALUES syntax:
```sql
INSERT INTO COMPANY (ID,NAME,AGE,ADDRESS,SALARY,JOIN_DATE) VALUES (4, 'Mark', 25, 'Rich-Mond ', 65000.00, '2007-12-13' ), (5, 'David', 27, 'Texas', 85000.00 , '2007-12-13');
```

All the above statements would create the following records in COMPANY table. Next chapter will teach you how to display all these records from a table.
```
testdb=# select * from company;
```

```sql

ID        NAME        AGE        ADDRESS     SALARY	   JOIN_DATE
----      ----------  -----      ----------  -------   --------
1         Paul        32         California  20000.0    2001-07-13
2         Allen       25         Texas                  2007-12-13
3         Teddy       23         Norway      20000.0
4         Mark        25         Rich-Mond   65000.0    2007-12-13
5         David       27         Texas       85000.0    2007-12-13
```
