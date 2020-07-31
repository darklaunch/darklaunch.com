Remove a leading string from a variable. The string after the number sign is removed from the variable.

```bash
$ mkdir -p /tmp/path/to/something/
$ cd /tmp/path/to/something/
$ echo $PWD
/tmp/path/to/something
$ echo "${PWD#/tmp}"
/path/to/something
```

---


Posted Dec 11, 2018.
https://www.darklaunch.com/2018/12/11/bash-remove-prefix-from-a-string-variable.html