To skip the system prompt for the administrator's password, edit the sudoers file using `visudo` add the following replacing "user" with your username:

```
# Don't prompt for password when using sudo.
user ALL=(ALL) NOPASSWD: ALL
```

This will modify the sudoers file to skip the sudo password prompt for the current user.

---

Posted Nov 20, 2012.

https://www.darklaunch.com/2012/11/20/skip-password-prompt-when-executing-sudo.html

---

1 comment

<ol><li><div>

anonymous &ndash; Jan 4, 2013<div>

Awesome, thnx! :)

</div></div></li></ol>