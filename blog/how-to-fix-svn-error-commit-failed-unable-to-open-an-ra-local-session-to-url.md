You may get this error if your svn repository moved:
```svn: Commit failed (details follow):
svn: Unable to open an ra_local session to URL
svn: Unable to open repository 'file:///path/to/repository'```

You will need to relocate your svn source repository.
Here's the scenario:
```Repository was located in:
file:///home/user/var/www/repositories/www.example.com/

Repository moved to:
file:///home/user/mounts/www.example.com/web/repository/

Files are located in:
/var/www/www.example.com/```

Open terminal and do the following to update the location of the repository:

Check where the current location of the repository is using:
```cd /var/www/www.example.com/
svn info```

Look for "Repository Root:" ("file:///home/user/var/www/repositories/www.example.com/")

Now to switch the repository root, do the following:
```cd /var/www/www.example.com/
svn switch --relocate file:///home/user/var/www/repositories/www.example.com/ file:///home/user/mounts/www.example.com/web/repository/```
That is, svn switch --relocate old_repo new_repo.

Again, do svn info to check that the repository root has been updated.
```svn info```

NOTE: Remember there are three (3) slashes after file in file:///