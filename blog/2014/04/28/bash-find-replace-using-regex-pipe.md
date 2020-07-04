<img alt="Bash Find & Replace" src="/img/uploads/2014-04/bash-find-replace-regex.png" />

Find & replace using regex on the command line using perl.
```sh
perl -pe "s/find/replace/g"
```
Parentheses for grouping and capturing is also supported.
```sh
$ echo "myfile.txt" | perl -pe "s/(.*)\.txt/\1.log/"
myfile.log
```
```sh
$ find=".*(\d{4})\/(\d{2})\/(\d{2})\/.*"
$ replace="year: \1; month: \2; day: \3"
$ echo "https://www.example.com/2014/04/28/page-slug" | perl -pe "s/${find}/${replace}/"
year: 2014; month: 04; day: 28
```