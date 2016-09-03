<p>Example error:</p>
<code>
Error running this command:

svn --non-interactive --config-dir /tmp list --xml 'file:///mnt/example/www.example.com/web/repository/@'

Unable to open an ra_local session to URL
Unable to open repository 'file:///mnt/example/www.example.com/web/repository'
Can't open file '/mnt/example/www.example.com/web/repository/format': Permission denied
</code>

<p>How to fix:</p>
<p>Edit quoteCommand() in ../include/command.php quoteCommand() should read:</p>

<code name="php">
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
</code>

<p>Add: else { $cmd = 'sudo -u root ' . $cmd; } to give svn permission.</p>