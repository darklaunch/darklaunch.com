Use list of arguments with pexpect.spawn instead of str.format.

```python
import pexpect

# Incorrect.
path = '/tmp/dir-without-spaces'
child = pexpect.spawn('ls {0}'.format(path))
print(child.read())
child.close()

# Error.
path = '/tmp/dir with spaces'
child = pexpect.spawn('ls {0}'.format(path))
print(child.read())
child.close()

# Also incorrect.
path = '/tmp/dir with spaces'
child = pexpect.spawn('ls "{0}"'.format(path))
print(child.read())
child.close()

# Correct.
path = '/tmp/dir with spaces'
child = pexpect.spawn('ls', [path])
print(child.read())
child.close()
```

```bash
$ mkdir -p "/tmp/dir-without-spaces"
$ mkdir -p "/tmp/dir with spaces"
$ touch "/tmp/dir-without-spaces/file"{1,2,3}".txt"
$ touch "/tmp/dir with spaces/file"{1,2,3}".txt"
$ python test.py
file1.txt  file2.txt  file3.txt

ls: cannot access '/tmp/dir': No such file or directory
ls: cannot access 'with': No such file or directory
ls: cannot access 'spaces': No such file or directory

file1.txt  file2.txt  file3.txt

file1.txt  file2.txt  file3.txt
```