# Bash get parent process pid

Get the parent id of a process using the ps command. Example:

```bash
$ my_child_id=41219
$ echo "parent id: $(ps -o ppid= ${my_child_id})"
parent id:   1
```

---

Posted Sep 21, 2019.

https://www.darklaunch.com/2019/09/21/bash-get-parent-process-pid.html