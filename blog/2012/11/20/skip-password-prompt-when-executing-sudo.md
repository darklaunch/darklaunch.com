To skip the system prompt for the administrator's password, add the following to your sudoers file:

```
# Don't prompt for password when using sudo.
user ALL=(ALL) NOPASSWD: ALL
```

This will modify the sudoers file to skip the sudo password prompt for the current user.

Or in one step, do this on the command line:

```
whoami=$(whoami)
sudo bash -c 'echo -e "# Don'\''t prompt for password when using sudo.\n'$whoami' ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers'
```

---

Posted Nov 20, 2012.
https://www.darklaunch.com/2012/11/20/skip-password-prompt-when-executing-sudo