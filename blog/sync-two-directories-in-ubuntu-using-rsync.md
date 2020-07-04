To sync two directories, use rsync with the following command:
```
rsync --recursive --verbose --delete --progress /from/this/source/ /to/this/destination/
```
To view the resulting changes without applying them, add the --dry-run option.
```
rsync --recursive --verbose --delete --progress --dry-run /from/this/source/ /to/this/destination/
```