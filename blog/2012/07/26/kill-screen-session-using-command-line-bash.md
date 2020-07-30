To kill an active screen, use the following command:

```bash
$ screen -S myscreen -X quit
```

To use this in a bash script, use the following:

```sh
# Kill screen if running
sessionname="myscreen"
if [ $(screen -list | grep "$sessionname" | wc --lines) -ge 1 ]; then
    echo "screen session $sessionname is running"
    screen -S "$sessionname" -X "quit"
fi
```

---

Posted Jul 26, 2012.
https://www.darklaunch.com/2012/07/26/kill-screen-session-using-command-line-bash