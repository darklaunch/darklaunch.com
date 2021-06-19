# Bash create alias starting with a dash

To create an alias that starts with a dash, use a double-dash to signify the end of the command options.

```bash
$ alias -foo="echo bar"
-bash: alias: -f: invalid option
alias: usage: alias [-p] [name[=value] ... ]
$ alias -- -foo="echo bar"
$ -foo
bar
```

<img alt="" src="/img/uploads/2014-01/bash-alias-starting-with-dash.png" />

---

Posted Jan 2, 2014.

https://www.darklaunch.com/2014/01/02/bash-create-alias-starting-with-a-dash.html