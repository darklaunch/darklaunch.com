# Git revert file to a specific commit or revision

Revert a file to a specific version, by using the `git checkout` command.

```bash
$ git checkout <commit> -- path/to/file.txt
```

For example, revert an icon to a previous state.

```bash
$ git checkout 807eff29 -- static/images/icons/world.svg
```

---

Posted Jan 10, 2019.

https://www.darklaunch.com/2019/01/10/git-revert-file-to-a-specific-commit-or-revision.html