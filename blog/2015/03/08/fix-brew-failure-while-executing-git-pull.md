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