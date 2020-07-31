Use sed to remove duplicate empty lines from a file and replace them with a single empty line.

```bash
remove_duplicate_empty_lines() {
    sed '/^$/N;/^\n$/D'
}
```

```bash
sed -i "" '/^$/N;/^\n$/D' input.txt
```

Example:

```bash
$ cat --number file.txt
     1	1
     2
     3
     4
     5	5
     6	6
     7
     8
     9	9

$ cat file.txt | sed '/^$/N;/^\n$/D' > modified.txt

$ cat --number modified.txt
     1	1
     2
     3	5
     4	6
     5
     6	9
```

---


Posted Jun 28, 2019.
https://www.darklaunch.com/2019/06/28/remove-duplicate-empty-lines-using-sed.html