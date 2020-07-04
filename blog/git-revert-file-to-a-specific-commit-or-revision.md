Revert a file to a specific version, by using the `git checkout' command.
```bash
$ git checkout <commit> -- path/to/file.txt
```
For example, revert an icon to a previous state.
```bash
$ git checkout 807eff29 -- static/images/icons/world.svg
```