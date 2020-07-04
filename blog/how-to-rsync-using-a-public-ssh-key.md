You can use `ssh -i identity_file' method with rsync by specifying the
remote shell to use.

```
$ rsync --rsh "ssh -i identity_file" --checksum --recursive --verbose --progress "myfolder" "ubuntu@10.20.1.10:/home/ubuntu/"```

Alternatively, modify your ssh config file. Add the following to your ~/.ssh/config file:

```
Host 10.20.1.10
Hostname 10.20.1.10
IdentityFile ~/.ssh/mykey
User ubuntu```

Now you can omit the "--rsh" parameter and do:

```
$ rsync --checksum --recursive --verbose --progress "myfolder" "ubuntu@10.20.1.10:/home/ubuntu/"```

And now passwordless ssh-ing into the machine also works with the ssh config additions. e.g.:

```
$ ssh 10.20.1.10```