Use the find command to locate certain files and grep to search for strings within the files found.

Find todo tasks in recently modified files:

```bash
$ find . -mmin -$((60*24)) -exec grep --color --with-filename "TODO" {} \;
```

---

Posted Jan 21, 2019.

https://www.darklaunch.com/2019/01/21/bash-find-and-grep-search-results.html