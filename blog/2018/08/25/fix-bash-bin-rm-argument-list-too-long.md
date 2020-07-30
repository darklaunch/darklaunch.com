Attempting to delete a large list of files may error with "Argument list too long".

```bash
$ rm *.log.*.gz
bash: /bin/rm: Argument list too long
```

The solution is to use the find command and pass the -delete option.

```bash
$ find -name "*.log.*.gz" -delete
```

Find the maximum number of arguments allowed:

```bash
$ getconf ARG_MAX
262144
```

---

Posted Aug 25, 2018.
https://www.darklaunch.com/2018/08/25/fix-bash-bin-rm-argument-list-too-long