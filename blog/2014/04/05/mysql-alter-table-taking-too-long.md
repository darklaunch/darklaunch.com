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