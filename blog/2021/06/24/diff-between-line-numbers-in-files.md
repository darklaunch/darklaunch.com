# Diff between line numbers in files

Run a `diff` between ranges of line numbers in files.

Adjust the variables as needed.

Set `file_1_name` and `file_2_name` to the same value when comparing line ranges within the same file. Set `file_1_name` and `file_2_name` to the different file names when comparing line ranges in two different files.

```bash
file_1_name="util.py"
file_1_start=80
file_1_end=142

file_2_name="util.py"
file_2_start=144
file_2_end=229
```

The difference is piped into `colordiff` to colorize the output. The colorized output is piped to `less` as a pager with the `-R` option for the color escape sequences to be displayed correctly.

```bash
diff \
    --recursive \
    --unified \
    <(sed -n "${file_1_start}","${file_1_end}p" "${file_1_name}") \
    <(sed -n "${file_2_start}","${file_2_end}p" "${file_2_name}") | colordiff | less -R
```

Additional output if debugging with`set -x` is enabled:

```
+ colordiff
+ less -R
++ sed -n 80,142p util.py
+ diff --recursive --unified /dev/fd/63 /dev/fd/62
++ sed -n 144,229p util.py
```

kw: diff, file descriptor, process substitution, anonymous pipe

---

Posted Jun 24, 2021.

https://www.darklaunch.com/2021/06/24/diff-between-line-numbers-in-files.html