Find files containing the Windows newline character (CRLF) and replace them with Unix newlines (LF).

```sh
$ find . -type f -exec perl -pi -e 's/\r\n|\n|\r/\n/g' {} \;
```