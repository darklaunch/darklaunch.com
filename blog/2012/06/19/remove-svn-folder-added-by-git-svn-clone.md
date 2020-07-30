If you accidentally added a .svn folder into your repository, you may get the "Failed to add directory" error when checking out the repository.

```bash
$ svn checkout http://www.example.com/svn/myproject/trunk/
>>> svn: E155000: Failed to add directory '../path/to/.svn': object of the same name as the administrative directory
```

To fix this, use the `svn del` command. For example:

```bash
$ svn del http://www.example.com/svn/myproject/trunk/path/to/.svn -m
"Remove .svn folder"
>>> Committed revision XXX.
```

You will now be able to successfully `svn checkout` the repository.

Please use git.

---

Posted Jun 19, 2012.
https://www.darklaunch.com/2012/06/19/remove-svn-folder-added-by-git-svn-clone