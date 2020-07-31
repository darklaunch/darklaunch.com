Use sed to remove lines starting at BEGIN and ending with END line markers.

```sh
$ cat myfile.txt
1
2
BEGIN IGNORE
4 this line should be ignored
5 and this should be ignored
6 ignore
7 ignore
8 ignore
END IGNORE
10
11
12
13
14
15
```

```sh
$ cat myfile.txt | sed '/BEGIN IGNORE/,/END IGNORE/d'
1
2
10
11
12
13
14
15
```

---


Posted Sep 9, 2016.
https://www.darklaunch.com/2016/09/09/bash-remove-section-of-string-using-sed.html