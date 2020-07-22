Quote a command with arguments in python using `pipes.quote()` and `shlex.quote()`. Example:

```python
import pipes

# Incorrect.
path = '/tmp/dir-without-spaces'
cmd = 'ls {0}'.format(path)

# Error.
path = '/tmp/dir with spaces'
cmd = 'ls {0}'.format(path)

# Also incorrect.
path = '/tmp/dir with spaces'
cmd = 'ls "{0}"'.format(path)

# Correct.
path = '/tmp/dir with spaces'
cmd = 'ls {0}'.format(pipes.quote(path))
```

Use `pipes.quote()` for python 2 and python 3.
Use `shlex.quote()` for python 3 only.