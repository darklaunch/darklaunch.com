To show a list of the files changed between git commits, do the following:

```
$ git diff --name-only SHA1 SHA2
```

To also, zip the resulting files, pipe the response to `xargs' and `zip' as such:

```
$ git diff --name-only SHA1 SHA2 | xargs zip /path/to/file.zip
```

<img alt="" src="/img/uploads/2012-09/git-diff-files-changed.png" />