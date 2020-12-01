Disable ipython's exit confirmation. Create an ipython profile.

```bash
$ ipython profile create
```

Change `TerminalInteractiveShell.confirm_exit` to False.

```
$ vim ~/.ipython/profile_default/ipython_config.py
c.TerminalInteractiveShell.confirm_exit = False
```

---

Posted Nov 10, 2015.

https://www.darklaunch.com/2015/11/10/disable-ipython-s-do-you-really-want-to-exit-y-n-confirmation.html