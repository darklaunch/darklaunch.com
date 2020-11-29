To share your localhost and allow files to be available from other computers, do the following:

Open httpd.conf by selecting the WampServer tray icon. Select "PHP" and "php.ini"

Change the lines "Deny from all" and the next line "Allow from 127.0.0.1" to just "Allow from all" and restart Apache.

To restart Apache: WampServer tray icon and "Restart All Services".

Now all computers on the network can access your pages served by your WampServer my going to http://&lt;your_ip_address&gt;/

To find your local network ip address, run ipconfig on the command line.

```
ipconfig
```

```
<Directory "c:/wamp/www/">
   #
   # Possible values for the Options directive are "None", "All",
   # or any combination of:
   #   Indexes Includes FollowSymLinks SymLinksifOwnerMatch ExecCGI MultiViews
   #
   # Note that "MultiViews" must be named *explicitly* --- "Options All"
   # doesn't give it to you.
   #
   # The Options directive is both complicated and important.  Please see
   # http://httpd.apache.org/docs/2.2/mod/core.html#options
   # for more information.
   #
   Options Indexes FollowSymLinks

   #
   # AllowOverride controls what directives may be placed in .htaccess files.
   # It can be "All", "None", or any combination of the keywords:
   #   Options FileInfo AuthConfig Limit
   #
   AllowOverride all

   #
   # Controls who can get stuff from this server.
   #

#   onlineoffline tag - don't remove
   Order Deny,Allow
   #Deny from all
   #Allow from 127.0.0.1
   Allow from all

</Directory>
```

---

Posted May 17, 2012.

https://www.darklaunch.com/2012/05/17/share-wamp-wampserver-localhost-files-on-same-network.html

---

1 comment

<ol><li><div>

anonymous &ndash; Dec 24, 2015<div>

Please update for new version of wamp

</div></div></li></ol>