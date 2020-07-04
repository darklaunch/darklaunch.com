Disable ipython's exit confirmation. Create an ipython profile.
```bash
$ ipython profile create
```
Change TerminalInteractiveShell.confirm_exit to False.
```
$ vim ~/.ipython/profile_default/ipython_config.py
c.TerminalInteractiveShell.confirm_exit = False
```