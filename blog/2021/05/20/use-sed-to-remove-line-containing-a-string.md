# Use sed to remove line containing a string

The `sed` command can be used to remove lines containing a keyword.

Remove line containing string from standard input:

```bash
$ echo -e "1\n2\n3"
```

```
1
2
3
```

```bash
$ echo -e "1\n2\n3" | sed "/2/d"
```

```
1
3
```

Remove line containing string from a file:

```bash
$ echo -e "1\n2\n3" > myfile.txt
```

```bash
$ cat myfile.txt
```

```
1
2
3
```

```bash
$ sed -i "" "/2/d" myfile.txt
```

```bash
$ cat myfile.txt
```

```
1
3
```

---

Posted May 20, 2021.

https://www.darklaunch.com/2021/05/20/use-sed-to-remove-line-containing-a-string.html