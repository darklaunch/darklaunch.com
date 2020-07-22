Run multiple exec commands with find.

The `find` command accepts multiple `-exec` parameters.

Example that looks in certain directories for a file with a keyword.
```
$ find . -type d ! -path . -exec echo "Searching in {}" \; -exec grep -Ri "keyword" {} \;
```