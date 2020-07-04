<p>You can use `ssh -i identity_file' method with rsync by specifying the
remote shell to use.</p>

<code>
$ rsync --rsh "ssh -i identity_file" --checksum --recursive --verbose --progress "myfolder" "ubuntu@10.20.1.10:/home/ubuntu/"</code>

<p>Alternatively, modify your ssh config file. Add the following to your ~/.ssh/config file:</p>

<code>
Host 10.20.1.10
Hostname 10.20.1.10
IdentityFile ~/.ssh/mykey
User ubuntu</code>

<p>Now you can omit the "--rsh" parameter and do:</p>

<code>
$ rsync --checksum --recursive --verbose --progress "myfolder" "ubuntu@10.20.1.10:/home/ubuntu/"</code>

<p>And now passwordless ssh-ing into the machine also works with the ssh config additions. e.g.:</p>

<code>
$ ssh 10.20.1.10</code>