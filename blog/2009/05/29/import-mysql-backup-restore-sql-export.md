<p>Import a mysql backup by doing the following on the command line:</p>

<code>mysql -u USERNAME -p -h SERVER DATABASE < "/path/to/backup.sql"</code>

<p>Replace USERNAME, SERVER, DATABASE and "/path/to/backup.sql".</p>

<code>mysql -u someuser -p -h 127.0.0.1 mydatabase < "~/Desktop/mybackup.sql"</code>

<p>To view the status of the import, check the process list.</p>

<code>$ mysql
mysql> show processlist;</code>