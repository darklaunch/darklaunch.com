To keep your ssh session from timing out, do the following:

Edit ssh_config
```
vi /etc/ssh/ssh_config
```
Append:
```
ServerAliveInterval 15
ServerAliveCountMax 3
```
Additionally, use the reconnect option:
```
sshfs myuser@ftp.mysite.com:/ ~/mnt/mysite -o reconnect
```