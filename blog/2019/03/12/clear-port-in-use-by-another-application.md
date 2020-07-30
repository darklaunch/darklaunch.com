Fix "bind: address already in use" error by finding the process in use and stopping it.

Example error message:

```bash
$ my_command
2019/04/24 17:09:14 listen tcp 127.0.0.1:3306: bind: address already in use
```

Stop the process using port 3306:

```bash
$ sudo kill $(sudo lsof -t -i:3306)
```

Alternate method:

Clear the port, by finding the process using the port.

For example, find a process using port 8000.

```bash
$ netstat -tulpn | grep 8000
```

Running the netstat command will show an id on the far right. Stop the process by passing this process id to the kill command.

For example, if the id was 3746, run the following command.

```bash
$ kill 3746
```

---

Posted Mar 12, 2019.
https://www.darklaunch.com/2019/03/12/clear-port-in-use-by-another-application