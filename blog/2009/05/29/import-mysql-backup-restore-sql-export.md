# Import MySQL Backup; Restore .SQL Export

Import a mysql backup by doing the following on the command line:

```
mysql -u USERNAME -p -h SERVER DATABASE < "/path/to/backup.sql"
```

Replace USERNAME, SERVER, DATABASE and "/path/to/backup.sql".

```
mysql -u someuser -p -h 127.0.0.1 mydatabase < "~/Desktop/mybackup.sql"
```

To view the status of the import, check the process list.

```
$ mysql
mysql> show processlist;
```

---

Posted May 29, 2009.

https://www.darklaunch.com/2009/05/29/import-mysql-backup-restore-sql-export.html