# Bash extract between two strings using sed

Extract between a start and an end string using `sed`.

The following will extract content between html comments in markdown (.md) files:

```bash
start='<!--'
end='-->'
find . -type "f" -name "*.md" -exec sed -n "/${start}/,/${end}/p" {} \;
```

---

Posted Sep 3, 2020.

https://www.darklaunch.com/2020/09/03/bash-extract-between-two-strings-using-sed.html