# Grep multiple strings in same file

Find multiple strings in the same file using grep. Pass the results of grep to xargs with grep.

Find files containing both the add() method and the create() method.

```bash
$ grep -r -l "def add(" . | xargs grep -l "def create("
./db/models/fields/related_descriptors.py
./contrib/contenttypes/fields.p
```

Edit the resulting files by enclosing the grep command in $().

```bash
$ vim $(grep -r -l "def add(" . | xargs grep -l "def create(")
```

---

Posted Dec 24, 2018.

https://www.darklaunch.com/2018/12/24/grep-multiple-strings-in-same-file.html