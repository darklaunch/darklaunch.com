# Bash find multiple file types: directories & symbolic links

To find two or more file types, use the logical OR operator.

```
$ find . -type d -o -type l
```

This example finds all directories and symbolic links in the current directory.

<img alt="" src="/img/uploads/2014-02/bash-find-multiple-types.png" />

---

Posted Feb 26, 2014.

https://www.darklaunch.com/2014/02/26/bash-find-multiple-file-types-directories-symbolic-links.html