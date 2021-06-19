# Linux diff exit code when using the less pager

Retrieve the `diff` exit code when using `diff` with the `less` pager.

The `diff` command returns an exit code of `0` when there is no difference and `1` when there is a difference.

No difference with exit code of `0`:

```bash
$ diff <(echo "abc") <(echo "abc") > /dev/null; echo "exit code: $?"
```

```
exit code: 0
```

Difference with exit code of `1`:

```bash
$ diff <(echo "abc") <(echo "def") > /dev/null; echo "exit code: $?"
```

```
exit code: 1
```

Solution: Save the diff result to a variable and use its exit code:

```bash
diff_result="$(diff --recursive --unified file1.txt file2.txt)"
exit_code="$?"
if [[ "${exit_code}" -eq 0 ]]; then
    echo "files are identical"
else
    echo "${diff_result}" | less -R
    echo "differences found"
fi
```

---

Posted May 11, 2021.

https://www.darklaunch.com/2021/05/11/linux-diff-exit-code-when-using-the-less-pager.html