Fix by installing mysql-server.

```bash
$ python manage.py dbshell
CommandError: You appear not to have the 'mysql' program installed or on your path.

$ which mysql
$ sudo apt-get install mysql-server
$ which mysql
/usr/bin/mysql

$ python manage.py dbshell
mysql>
```

---

Posted Sep 7, 2014.
https://www.darklaunch.com/2014/09/07/fix-commanderror-you-appear-not-to-have-the-mysql-program-installed-or-on-your-path