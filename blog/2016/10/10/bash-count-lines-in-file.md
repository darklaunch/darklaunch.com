Use wc or grep to count the number of lines.

```
$ echo "" | wc -l
1

$ echo "a" | wc -l
1

$ echo -e "a\n" | wc -l
2

$ echo -e "a\nb" | wc -l
2

$ echo -e "a\nb\n" | wc -l
3

$ echo -e "a\nb\nc" | wc -l
3

$ echo -e "a\nb\nc\n" | wc -l
4
```

```
$ echo "" | grep --count ^
1

$ echo "a" | grep --count ^
1

$ echo -e "a\n" | grep --count ^
2

$ echo -e "a\nb" | grep --count ^
2

$ echo -e "a\nb\n" | grep --count ^
3

$ echo -e "a\nb\nc" | grep --count ^
3

$ echo -e "a\nb\nc\n" | grep --count ^
4
```

---


Posted Oct 10, 2016.
https://www.darklaunch.com/2016/10/10/bash-count-lines-in-file.html