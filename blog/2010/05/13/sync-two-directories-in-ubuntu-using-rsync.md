To sync two directories, use rsync with the following command:
```
rsync --recursive --verbose --delete --progress /from/this/source/ /to/this/destination/
```

To view the resulting changes without applying them, add the --dry-run option.
```
rsync --recursive --verbose --delete --progress --dry-run /from/this/source/ /to/this/destination/
```

---

Posted May 13, 2010.
https://www.darklaunch.com/2010/05/13/sync-two-directories-in-ubuntu-using-rsync