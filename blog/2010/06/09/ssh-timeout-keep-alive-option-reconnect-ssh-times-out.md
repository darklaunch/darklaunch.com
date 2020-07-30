To keep your ssh session from timing out, do the following:

Edit ssh_config:

```bash
$ vim /etc/ssh/ssh_config
```

Append:

```
ServerAliveInterval 15
ServerAliveCountMax 3
```

Additionally, use the reconnect option:

```bash
$ sshfs myuser@ftp.mysite.com:/ ~/mnt/mysite -o reconnect
```

---

Posted Jun 9, 2010.
https://www.darklaunch.com/2010/06/09/ssh-timeout-keep-alive-option-reconnect-ssh-times-out