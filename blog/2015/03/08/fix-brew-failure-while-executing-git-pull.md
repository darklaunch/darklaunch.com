# Fix brew "Failure while executing: git pull"

To fix brew "Failure while executing: git pull":

```
$ sudo chmod -R 777 /usr/local/
$ cd /usr/local/
$ git config core.filemode false
$ git stash -u
$ git fetch
$ git merge origin/master
```

Possible errors that this fixes:

"Error: Failed to update tap: foo/bar"
"error: Your local changes to the following files would be overwritten by merge:"
"Please, commit your changes or stash them before you can merge."

---

Posted Mar 8, 2015.

https://www.darklaunch.com/2015/03/08/fix-brew-failure-while-executing-git-pull.html