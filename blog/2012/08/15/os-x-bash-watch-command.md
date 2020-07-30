To run a command similar to the Linux "watch" command on Mac OSX, do the following:

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
https://www.darklaunch.com/2012/08/15/os-x-bash-watch-command