To fix the "ImportError: Bad magic number" error, you will need to remove existing .pyc compiled python files.

```bash
$ find . -name "*.pyc" -delete
```

Alternatively, if you'd like to run some other command on the files found, use the following syntax:

```bash
$ find . -name "*.pyc" -exec rm {} \;
```

---

Posted Apr 25, 2012.

https://www.darklaunch.com/2012/04/25/fix-importerror-bad-magic-number-in-path-to-file-pyc.html