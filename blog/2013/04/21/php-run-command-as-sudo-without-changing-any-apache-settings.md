Here is how to run a php script as sudo without changing apache settings.

Save the following snippet as `receiver.sh`. This will act as the receiving script to run commands with sudo permissions.

```sh
#!/bin/bash

while :; do
    command=$(nc -l 1234)

    # "[Sun Apr 21 14:46:34 PDT 2013] ":command""
    echo "["$(date)"] \"${command}\""

    # Run command received with sudo permissions
    sudo -i "${command}"

    echo -e "\nreturn code: ${?}"
done
```

Run this script with sudo and keep the script running:

```sh
$ sudo bash receiver.sh
```

Now send a command to be run. Here are two examples to issue commands:

Inside a php script

```php
<?php
$data = 'whoami'; // Command to send
$fp = stream_socket_client('tcp://127.0.0.1:1234');
fwrite($fp, $data);
fclose($fp);
```

On the command line

```sh
$ echo "whoami" >/dev/tcp/localhost/1234
```

Example response:

```sh
$ sudo bash receiver.sh 
[Sun Apr 21 16:16:54 PDT 2013] "whoami"
root

return code: 0
```

<img alt="" src="/img/uploads/2013-04/run-php-sudo.png" />

---

Posted Apr 21, 2013.

https://www.darklaunch.com/2013/04/21/php-run-command-as-sudo-without-changing-any-apache-settings.html