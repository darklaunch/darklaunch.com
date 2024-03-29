# Bash kill shell script running in background

Kill a running script using the parent process id.

```bash
$ cat myscript.sh 
while :; do
    date
    sleep 1
done
```

```
$ bash myscript.sh
Sun Dec 10 00:00:00 PST 2017
Sun Dec 10 00:00:01 PST 2017
Sun Dec 10 00:00:02 PST 2017
Sun Dec 10 00:00:03 PST 2017
...
```

Find the parent process id in the 3rd column. It contains the value for the PPID (parent process id).

```bash
$ ps lux | head -1
  UID   PID  PPID CPU PRI NI      VSZ    RSS WCHAN  STAT   TT       TIME COMMAND          USER  %CPU %MEM STARTED
```

```bash
$ ps lux | grep sleep
  501 16357 16313   0  31  0  4267768   1000 -      S+   s002    0:00.01 sleep 1          user   0.1  0.0 00:00AM
  501 16359 15647   0  31  0  4259052    288 -      R+   s001    0:00.00 grep sleep       user   0.0  0.0 00:00AM
```

Use the kill command on the PPID and it will stop the child process. Ignore the line containing the process ids for the grep command.

```bash
$ kill 16313
```

The child process is terminated.

```bash
...
Sun Dec 10 00:00:04 PST 2017
Sun Dec 10 00:00:05 PST 2017
Sun Dec 10 00:00:06 PST 2017
Sun Dec 10 00:00:07 PST 2017
Sun Dec 10 00:00:08 PST 2017
Terminated: 15
```

If the process is not terminated, you might try -9 or sudo.

```bash
$ kill -9 $ppid
$ sudo kill $ppid
$ sudo kill -9 $ppid
```

---

Posted Dec 10, 2017.

https://www.darklaunch.com/2017/12/10/bash-kill-shell-script-running-in-background.html