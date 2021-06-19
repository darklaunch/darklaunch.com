# git show list of all files changed between two commits & zip them

To show a list of the files changed between git commits, do the following:

```bash
$ git diff --name-only SHA1 SHA2
```

To also, zip the resulting files, pipe the response to `xargs` and `zip` as such:

```bash
$ git diff --name-only SHA1 SHA2 | xargs zip /path/to/file.zip
```

<img alt="" src="/img/uploads/2012-09/git-diff-files-changed.png" />

---

Posted Sep 29, 2012.

https://www.darklaunch.com/2012/09/29/git-show-list-of-all-files-changed-between-two-commits-zip-them.html