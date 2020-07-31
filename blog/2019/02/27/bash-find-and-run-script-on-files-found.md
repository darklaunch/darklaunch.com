Find files using the find command and pass results to a script.

```bash
$ find $(pwd) -type f -name "*.csv" -exec php ~/process_file.php {} \;
```

Note: Use `find $(pwd)` instead of current directory `find .` so that the full path of each file found is passed to the script.

```php
<?php
// process_file.php
$filename = $argv['1'];
echo 'filename: ' . $filename . "\n";
```

```bash
$ find $(pwd) -type f -name "*.csv" -exec php ~/process_file.php {} \;
filename: /tmp/test/1.csv
filename: /tmp/test/3.csv
filename: /tmp/test/2.csv
```

---

Posted Feb 27, 2019.

https://www.darklaunch.com/2019/02/27/bash-find-and-run-script-on-files-found.html