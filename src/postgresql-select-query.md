**PostgreSQL - SELECT Query**

PostgreSQL SELECT statement is used to fetch the data from a database table which returns data in the form of result table. These result tables are called result-sets.

Syntax:
The basic syntax of SELECT statement is as follows:
```sql
SELECT column1, column2, columnN FROM table_name;
```

Here, column1, column2...are the fields of a table, whose values you want to fetch. If you want to fetch all the fields available in the field then you can use the following syntax:
```sql
SELECT * FROM table_name;
```

Example:
Consider the table COMPANY having records as follows:
```sql
 id | name  | age | address   | salary
----+-------+-----+-----------+--------
  1 | Paul  |  32 | California|  20000
  2 | Allen |  25 | Texas     |  15000
  3 | Teddy |  23 | Norway    |  20000
  4 | Mark  |  25 | Rich-Mond |  65000
  5 | David |  27 | Texas     |  85000
  6 | Kim   |  22 | South-Hall|  45000
  7 | James |  24 | Houston   |  10000
(7 rows)
```

Following is an example, which would fetch ID, Name and Salary fields of the customers available in CUSTOMERS table:
```sql
testdb=# SELECT ID, NAME, SALARY FROM COMPANY ;
This would produce the following result:

  id | name  | salary
 ----+-------+--------
   1 | Paul  |  20000
   2 | Allen |  15000
   3 | Teddy |  20000
   4 | Mark  |  65000
   5 | David |  85000
   6 | Kim   |  45000
   7 | James |  10000
(7 rows)
```

If you want to fetch all the fields of CUSTOMERS table, then use the following query:
```sql
testdb=# SELECT * FROM COMPANY;
This would produce the following result:

 id | name  | age | address   | salary
----+-------+-----+-----------+--------
  1 | Paul  |  32 | California|  20000
  2 | Allen |  25 | Texas     |  15000
  3 | Teddy |  23 | Norway    |  20000
  4 | Mark  |  25 | Rich-Mond |  65000
  5 | David |  27 | Texas     |  85000
  6 | Kim   |  22 | South-Hall|  45000
  7 | James |  24 | Houston   |  10000
(7 rows)
```
