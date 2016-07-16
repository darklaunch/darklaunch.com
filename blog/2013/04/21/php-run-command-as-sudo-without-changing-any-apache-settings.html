<p>Here is how to run a php script as sudo without changing apache settings.</p>

<p>Save the following snippet as <em>receiver.sh</em>. This will act as the receiving script to run commands with sudo permissions.</p>

<code name="sh">
#!/bin/bash

while :; do
    command=$(nc -l 1234)

    # "[Sun Apr 21 14:46:34 PDT 2013] ":command""
    echo "["$(date)"] \"${command}\""

    # Run command received with sudo permissions
    sudo -i "${command}"

    echo -e "\nreturn code: ${?}"
done
</code>

<p>Run this script with sudo and keep the script running:</p>

<code>$ sudo bash receiver.sh</code>

<p>Now send a command to be run. Here are two examples to issue commands:</p>

<p>Inside a php script</p>

<code name="php">
<?php
$data = 'whoami'; // Command to send
$fp = stream_socket_client('tcp://127.0.0.1:1234');
fwrite($fp, $data);
fclose($fp);
</code>

<p>On the command line</p>

<code name="sh">
$ echo "whoami" >/dev/tcp/localhost/1234
</code>

<p>Example response:</p>

<code>
$ sudo bash receiver.sh 
[Sun Apr 21 16:16:54 PDT 2013] "whoami"
root

return code: 0</code>

<img alt="" src="/img/uploads/2013-04/run-php-sudo.png" />