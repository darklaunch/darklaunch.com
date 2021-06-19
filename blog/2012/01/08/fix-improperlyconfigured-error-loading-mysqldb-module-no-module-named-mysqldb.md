# Fix ImproperlyConfigured: Error loading MySQLdb module: No module named MySQLdb

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

---

5 comments

<ol><li><div>

anonymous &ndash; Aug 3, 2012<div>

Hi,
I have tried many different things and install MySQLdb. If I type from the interpreter import MySQLdb it works. But when I try to do it using DJANGO it fails giving this error

<class 'django.core.exceptions.ImproperlyConfigured'>: Error loading MySQLdb module: No module named MySQLdb 
      args = ('Error loading MySQLdb module: No module named MySQLdb',) 
      message = 'Error loading MySQLdb module: No module named MySQLdb'

</div></div></li><li><div>

anonymous &ndash; Feb 15, 2013<div>

For OS X, enter this on the command line before proceeding with the install.

`export PATH=/usr/local/mysql/bin:$PATH`

</div></div></li><li><div>

anonymous &ndash; Mar 13, 2013<div>

Thank you so much for this! Exactly what I have been looking for! So many people have crazy methods but all that was needed was two lines -_-

</div></div></li><li><div>

anonymous &ndash; Feb 14, 2014<div>

django.core.exceptions.ImproperlyConfigured: Error loading MySQLdb module: this is MySQLdb version (1, 2, 3, 'final', 0), but _mysql is version (1, 2, 5, 'final', 1)

instead of 
`$ pip install MySQL-python`

install the matching version.
`$ pip install MySQL-python==1.2.3`

then

`django.core.exceptions.ImproperlyConfigured: Error loading MySQLdb module: _mysql: init failed`

unfortunately, this one fixed itself somehow. i just opened up a new command line window in Ubuntu without going into the virtualenv and it worked.

</div></div></li><li><div>

anonymous &ndash; Apr 4, 2016<div>

For Python 3 use mysqlclient:
`$ pip install mysqlclient`

Possible errors:
- ImportError: No module named 'ConfigParser' (from ConfigParser import SafeConfigParser)
- SyntaxError: invalid syntax (_KEYCRE = re.compile(ur"%\(([^)]+)\)s"))

https://docs.djangoproject.com/en/dev/ref/databases/#mysql-db-api-drivers

</div></div></li></ol>