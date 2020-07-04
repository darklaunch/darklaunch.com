Allow access to MySQL database from remote server.

Edit /etc/mysql/my.cnf or /usr/local/mysql/my.cnf (on OS X)

Change
```
bind-address = 127.0.0.1
```
to
```
bind-address = 0.0.0.0
```
Restart MySQL
```
$ sudo service mysql stop
$ sudo service mysql start
$ sudo service mysql status
```
or
```
$ sudo mysqladmin shutdown
$ /usr/local/mysql/bin/mysqld
```
Fixes for possible error:

Fix "Host is not allowed to connect to this MySQL server"
$ mysql -u root -h "www.example.com"
ERROR 1130 (HY000): Host 'dhcp-XXX-XX-XX-XXX.example.com' is not allowed to connect to this MySQL server
```sql
$ mysql -u root
mysql> GRANT ALL ON *.* TO 'root'@'%';
```