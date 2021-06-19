# SVN Move multiple files; CMD; command line

```bash
for %i in (*.php) do svn move "C:\wamp\www\old_dir\%i" "C:\wamp\www\new_dir"
```

```bash
for i in *.js; do svn mv "$i" "/var/www/www.example.com/include/js/old/"; done
```

> Note: Please use git.

---

Posted Feb 20, 2009.

https://www.darklaunch.com/2009/02/20/svn-move-multiple-files-cmd-command-line.html