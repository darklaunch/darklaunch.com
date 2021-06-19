# How to prompt for password when running command over ssh

To prompt for password when running a command over an ssh connect, allocate pseudo terminal using the `-t` flag

```bash
$ ssh -t remote.server "sudo reboot now"
[sudo] password for user:
Connection to remote.server closed.
```

Without using the `-t` flag, an error will appear:

```bash
$ ssh remote.server "sudo reboot now"
sudo: a terminal is required to read the password; either use the -S option to read from standard input or configure an askpass helper
```

---

Posted Jan 2, 2021.

https://www.darklaunch.com/2021/01/02/how-to-prompt-for-password-when-running-command-over-ssh.html