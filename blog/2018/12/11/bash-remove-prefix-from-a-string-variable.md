Remove a leading string from a variable. The string after the number sign is removed from the variable.

```bash
$ mkdir -p /tmp/path/to/something/
$ cd /tmp/path/to/something/
$ echo $PWD
/tmp/path/to/something
$ echo "${PWD#/tmp}"
/path/to/something
```