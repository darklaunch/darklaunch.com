# Bash why quotes are important for variables; preserve newlines, line endings

```sh
#!/bin/bash

str=$(cat <<EOF
foo
bar
baz
EOF
)

echo $str
echo "$str"
```

Newlines are ignored when echoing the variable without surrounding quotes. Newlines are preserved when using echo and quoting the variable. The script produces the following output.

```sh
foo bar baz
foo
bar
baz
```

---

Posted Dec 14, 2010.

https://www.darklaunch.com/2010/12/14/bash-why-quotes-are-important-for-variables-preserve-newlines-line-endings.html