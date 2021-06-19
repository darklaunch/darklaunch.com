# OS X bash 'watch' command

To run a command similar to the Linux `watch` command on Mac OSX, do the following:

```sh
while :; do your_command; done
```

For example, the following will check the disk usage for the current directory via `du` every two seconds. The `echo -ne "\r"` causing the line to write over itself replacing the existing line.

```sh
while :; do echo -ne " "$(du -s .)"\r"; sleep 2s; done
```

<img alt="" src="/img/uploads/2012-08/bash-osx-watch-command.png" />

---

Posted Aug 15, 2012.

https://www.darklaunch.com/2012/08/15/os-x-bash-watch-command.html

---

2 comments

<ol><li><div>

anonymous &ndash; Jul 16, 2016<div>

See also `watch_file()` command in https://github.com/dot-star/dot-star/blob/master/bash/.aliases.sh#L439

</div></div></li><li><div>

anonymous &ndash; Aug 24, 2019<div>

See also https://www.darklaunch.com/watch-files-and-run-a-command

</div></div></li></ol>