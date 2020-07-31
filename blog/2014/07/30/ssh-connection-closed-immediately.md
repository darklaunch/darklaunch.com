To determine why the ssh connection closes immediately, try running ssh daemon on the remote computer with the verbose debugging turned on. Then look at the logging output. If it contains "key_from_blob: can't read rsa key", you may have incorrectly copied and pasted the key.

```bash
$ /usr/sbin/sshd -d
```

If sshd is located elsewhere, use the following:

```bash
$ $(which sshd) -d
```

Things to try on the local machine trying to connect to the remote machine:

If you keep getting "Enter passphrase for key" and there is no passphrase, you may be incorrectly pointing to the public key.
debug1: key_parse_private2: missing begin marker
debug1: key_parse_private_pem: PEM_read_PrivateKey failed

instead of:
```bash
$ ssh -v user@host -i ~/.ssh/id_rsa.pub
```

do this:
```bash
$ ssh -v user@host -i ~/.ssh/id_rsa
```

* use `ssh -v'  to enable verbose mode. This will show you what authentications methods attempted and the corresponding files read, among other things.

Things to try on the remote machine that you are trying to connect to using ssh:

Ensure that the ssh daemon is running:
```bash
$ sudo /etc/init.d/ssh status
* sshd is not running
$ sudo /etc/init.d/ssh start
* Starting OpenBSD Secure Shell server sshd
```

* Ensure that wrapping is off in vim (or editor) if editing the authorized_keys file manually
* Ensure that no spaces exist in authorized_keys file
* Ensure that the correct authorized_keys file exists and is readable
by the ssh deamon (sshd) using sshd with the -d Debug mode enabled

Possible errors: "debug1: Could not open authorized keys '/.../.ssh/authorized_keys2': No such file or directory"

---


Posted Jul 30, 2014.
https://www.darklaunch.com/2014/07/30/ssh-connection-closed-immediately.html