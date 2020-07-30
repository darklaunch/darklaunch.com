Using the command string, parse command into a list of arguments.

```python
$ python
>>> import shlex
>>> cmd = '/usr/bin/binary -v --recursive --exclude=".git"'
>>> shlex.split(cmd)
['/usr/bin/binary', '-v', '--recursive', '--exclude=.git']
```

Using a list of arguments, reconstruct the command executed into a string.

```python
$ python
>>> import subprocess
>>> cmd_list = ['/usr/bin/binary', '-v', '--recursive', '--exclude=.git']
>>> subprocess.list2cmdline(cmd_list)
'/usr/bin/binary -v --recursive --exclude=.git'
```

---

Posted Feb 24, 2017.
https://www.darklaunch.com/2017/02/24/python-subprocess-print-command-with-arguments