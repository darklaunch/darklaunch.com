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

<ol>
    <li>
        <div>
            anonymous &ndash; Aug 3, 2012
            <div>
                <p>Hi,</p><p>I have tried many different things and install MySQLdb. If I type from the interpreter import MySQLdb it works. But when I try to do it using DJANGO it fails giving this error</p><p></p><p>: Error loading MySQLdb module: No module named MySQLdb </p><p>&nbsp;&nbsp;&nbsp;&nbsp;  args = ('Error loading MySQLdb module: No module named MySQLdb',) </p><p>&nbsp;&nbsp;&nbsp;&nbsp;  message = 'Error loading MySQLdb module: No module named MySQLdb'</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 15, 2013
            <div>
                <p>For OS X, enter this on the command line before proceeding with the install.</p><p></p><p>export PATH=/usr/local/mysql/bin:$PATH</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Mar 13, 2013
            <div>
                <p>Thank you so much for this! Exactly what I have been looking for! So many people have crazy methods but all that was needed was two lines -_-</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 14, 2014
            <div>
                <p>django.core.exceptions.ImproperlyConfigured: Error loading MySQLdb module: this is MySQLdb version (1, 2, 3, 'final', 0), but _mysql is version (1, 2, 5, 'final', 1)</p><p></p><p>instead of </p><p>$ pip install MySQL-python</p><p></p><p>install the matching version.</p><p>$ pip install MySQL-python==1.2.3</p><p></p><p>then</p><p></p><p>django.core.exceptions.ImproperlyConfigured: Error loading MySQLdb module: _mysql: init failed</p><p></p><p>unfortunately, this one fixed itself somehow. i just opened up a new command line window in Ubuntu without going into the virtualenv and it worked.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 4, 2016
            <div>
                <p>For Python 3 use mysqlclient:</p><p>$ pip install mysqlclient</p><p></p><p>Possible errors:</p><p>- ImportError: No module named 'ConfigParser' (from ConfigParser import SafeConfigParser)</p><p>- SyntaxError: invalid syntax (_KEYCRE = re.compile(ur"%\(([^)]+)\)s"))</p><p></p><p><a href="https://docs.djangoproject.com/en/dev/ref/databases/#mysql-db-api-drivers">https://docs.djangoproject.com/en/dev/ref/databases/#mysql-db-api-drivers</a></p>
            </div>
        </div>
    </li>
</ol>
