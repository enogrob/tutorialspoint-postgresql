**PostgreSQL - DROP Table**

The PostgreSQL DROP TABLE statement is used to remove a table definition and all associated data, indexes, rules, triggers, and constraints for that table.

You have to be careful while using this command because once a table is deleted then all the information available in the table would also be lost forever.

**Syntax**
Basic syntax of DROP TABLE statement is as follows.
```sql
DROP TABLE table_name;
```

**Example**
We had created the tables DEPARTMENT and COMPANY in the previous chapter. First verify these tables (use \d to list the tables):
```
$ psql postgres

postgres=# \l
                                     List of databases
             Name             |  Owner  | Encoding | Collate | Ctype |  Access privileges
------------------------------+---------+----------+---------+-------+---------------------
 db/ruby_thursday_development | enogrob | UTF8     | C       | UTF-8 |
 db/ruby_thursday_production  | enogrob | UTF8     | C       | UTF-8 |
 db/ruby_thursday_test        | enogrob | UTF8     | C       | UTF-8 |
 enogrob                      | enogrob | UTF8     | C       | UTF-8 |
 postgres                     | enogrob | UTF8     | C       | UTF-8 |
 taski_development            | enogrob | UTF8     | C       | UTF-8 |
 taski_production             | taski   | UTF8     | C       | UTF-8 |
 taski_test                   | enogrob | UTF8     | C       | UTF-8 |
 template0                    | enogrob | UTF8     | C       | UTF-8 | =c/enogrob         +
                              |         |          |         |       | enogrob=CTc/enogrob
 template1                    | enogrob | UTF8     | C       | UTF-8 | =c/enogrob         +
                              |         |          |         |       | enogrob=CTc/enogrob
 testdb                       | enogrob | UTF8     | C       | UTF-8 |
(11 rows)

postgres=# \c testdb
You are now connected to database "testdb" as user "enogrob".

testdb-# \d
This would produce the following result:

           List of relations
 Schema |    Name    | Type  |  Owner
--------+------------+-------+----------
 public | company    | table | postgres
 public | department | table | postgres
(2 rows)
```

This means DEPARTMENT and COMPANY tables are present. So let us drop them as follows:
```sql
testdb=# drop table department, company;

```
This would produce the following result:
```
DROP TABLE
testdb=# \d
 relations found.
testdb=#
```

The message returned DROP TABLE indicates that drop command had been executed successfully.
