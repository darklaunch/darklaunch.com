To fix the "ImportError: Bad magic number" error, you will need to remove existing .pyc compiled python files.

```
$ find . -name "*.pyc" -delete
```

Alternatively, if you'd like to run some other command on the files found, use the following syntax:

```
$ find . -name "*.pyc" -exec rm {} \;
```