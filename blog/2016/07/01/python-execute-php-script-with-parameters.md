Call php code from a Python script. The following Python script executes a PHP script and outputs the results.

```python
# script.py
import subprocess

php_script = 'var_dump(stream_get_contents(STDIN));'
command = ['php', '-r', php_script,]
proc = subprocess.Popen(command, shell=False, stdout=subprocess.PIPE, stdin=subprocess.PIPE)
stdout, stderr = proc.communicate(input='hello, world!')
print stdout
```

```bash
$ python script.py
string(13) "hello, world!"
```

Note: Python 3 may require input value to be string encoded using str.encode().

```python
try:
    # Python 3
    input = str.encode(modified)
except TypeError:
    # Python 2
    input = modified
```