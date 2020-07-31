To fix the "No module named MySQLdb" error, you need to install MySQL support for Python; do the following:

```sh
pip install MySQL-python
```

NOTE: Don't use sudo with pip. Fix your directory permissions if you find yourself needing to use sudo.

Other errors:

```
EnvironmentError: mysql_config not found
```
fix with:
```
sudo apt-get install libmysqlclient15-dev
```

```
Python.h: No such file or directory
```
fix with
```
sudo apt-get install python2.7-dev
```

---

Posted Jan 8, 2012.

https://www.darklaunch.com/2012/01/08/fix-improperlyconfigured-error-loading-mysqldb-module-no-module-named-mysqldb.html