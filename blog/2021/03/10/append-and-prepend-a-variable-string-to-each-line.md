# Append and prepend a variable string to each line

Use `sed` to either append or prepend a variable string to each input line.

Append a string to each input line:

```bash
$ my_input_string="$(echo -e "a\nb\nc")"
$ echo "${my_input_string}"
```

```
a
b
c
```

```bash
$ thing_to_append=" - my appended string"
$ echo "${my_input_string}" | sed -e "s#\$#${thing_to_append}#"
```

```
a - my appended string
b - my appended string
c - my appended string
```

Prepend a string to each input line:

```bash
$ my_input_string="$(echo -e "a\nb\nc")"
$ echo "${my_input_string}"
```

```
a
b
c
```

```bash
$ thing_to_prepend="my prepended string - "
$ echo "${my_input_string}" | sed -e "s#^#${thing_to_prepend}#"
```

```
my prepended string - a
my prepended string - b
my prepended string - c
```

Hint: The `sed` command allows using an alternative delimiter for the substitute command. The pipe character `|` and the hash `#` can be good choices.

---

Posted Mar 10, 2021.

https://www.darklaunch.com/2021/03/10/append-and-prepend-a-variable-string-to-each-line.html