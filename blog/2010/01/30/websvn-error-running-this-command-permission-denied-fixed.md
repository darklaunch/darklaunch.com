Example error:
```
Error running this command:

svn --non-interactive --config-dir /tmp list --xml 'file:///mnt/example/www.example.com/web/repository/@'

Unable to open an ra_local session to URL
Unable to open repository 'file:///mnt/example/www.example.com/web/repository'
Can't open file '/mnt/example/www.example.com/web/repository/format': Permission denied
```

How to fix:
Edit quoteCommand() in ../include/command.php quoteCommand() should read:

```php
function quoteCommand($cmd) {
    global $config;

    // On Windows machines, the whole line needs quotes round it so that it's
    // passed to cmd.exe correctly

    if ($config->serverIsWindows) {
        $cmd = '"'.$cmd.'"';
    } else {
        $cmd = 'sudo -u root ' . $cmd;
    }

    return $cmd;
}
```

Add: else { $cmd = 'sudo -u root ' . $cmd; } to give svn permission.

---

Posted Jan 30, 2010.

https://www.darklaunch.com/2010/01/30/websvn-error-running-this-command-permission-denied-fixed.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Sep 3, 2010
            <div>

chown www-data /path/to/directory
would work too i believe

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 30, 2011
            <div>

also add to /etc/sudoers file:
www-data ALL=(ALL) NOPASSWD:ALL

sudo bash -c 'echo -e "www-data ALL=(ALL) NOPASSWD:ALL" &gt;&gt; /etc/sudoers'

            </div>
        </div>
    </li>
</ol>
