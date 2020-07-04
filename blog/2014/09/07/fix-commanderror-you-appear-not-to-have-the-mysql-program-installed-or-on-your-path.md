Fix by installing mysql-server.
```
$ python manage.py dbshell
CommandError: You appear not to have the 'mysql' program installed or on your path.

$ which mysql
$ sudo apt-get install mysql-server
$ which mysql
/usr/bin/mysql

$ python manage.py dbshell
mysql>
```