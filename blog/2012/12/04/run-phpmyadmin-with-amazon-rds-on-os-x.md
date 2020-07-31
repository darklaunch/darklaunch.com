To connect to an Amazon RDS instance on OS X, do the following:

```
# cd to www root
cd /Library/WebServer/Documents

# download and extract phpMyAdmin
wget "http://downloads.sourceforge.net/project/phpmyadmin/phpMyAdmin/3.5.3/phpMyAdmin-3.5.3-all-languages.tar.gz"
gunzip phpMyAdmin-3.5.3-all-languages.tar.gz
tar xvf phpMyAdmin-3.5.3-all-languages.tar

# symlink to /phpmyadmin
ln -s /Library/WebServer/Documents/phpMyAdmin-3.5.3-all-languages/ /Library/WebServer/Documents/phpmyadmin

# edit configuration
cd phpmyadmin
cp config.sample.inc.php config.inc.php
vim config.inc.php

# edit host:
$cfg['Servers'][$i]['host'] = 'xxxxxxxxx.xxxxxxxxxxxx.us-east-1.rds.amazonaws.com';
```

Login to Amazon RDS admin ( https://console.aws.amazon.com/rds/ ) and go to "DB Security Groups" to add a "CIDR/IP" with the ip address you'll be connecting from. (e.g. 12.34.567.89/32)

Go to http://127.0.0.1/phpmyadmin/

---


Posted Dec 4, 2012.
https://www.darklaunch.com/2012/12/04/run-phpmyadmin-with-amazon-rds-on-os-x.html