To find two or more file types, use the logical OR operator.

```
$ find . -type d -o -type l
```

This example finds all directories and symbolic links in the current directory.

<img alt="" src="/img/uploads/2014-02/bash-find-multiple-types.png" />