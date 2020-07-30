Find files containing the Windows newline character (CRLF) and replace them with Unix newlines (LF).

```sh
$ find . -type f -exec perl -pi -e 's/\r\n|\n|\r/\n/g' {} \;
```

---

Posted Jun 12, 2020.
https://www.darklaunch.com/2020/06/12/replace-crlf-with-lf-in-list-a-files-using-the-find-command