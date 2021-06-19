# MySQL ALTER TABLE taking too long

If the MySQL ALTER TABLE command is taking too long, this may help.

```sql
show processlist;
```

If you see "Waiting for table metadata lock", you may attempt to kill other processes.

```sql
kill 1372
```

Then proceed with your ALTER TABLE MySQL query.

```sql
SHOW DATABASES;
USE `mydatabase`;
ALTER TABLE `mytable` DROP `thecolumn`;
```

---

Posted Apr 5, 2014.

https://www.darklaunch.com/2014/04/05/mysql-alter-table-taking-too-long.html