<p>To fix brew "Failure while executing: git pull":</p>

<code>
$ sudo chmod -R 777 /usr/local/
$ cd /usr/local/
$ git config core.filemode false
$ git stash -u
$ git fetch
$ git merge origin/master</code>

<p>Possible errors that this fixes:</p>

<p>"Error: Failed to update tap: foo/bar"</p>
<p>"error: Your local changes to the following files would be overwritten by merge:"</p>
<p>"Please, commit your changes or stash them before you can merge."</p>