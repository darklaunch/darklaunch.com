Get the parent id of a process using the ps command. Example:
```bash
$ my_child_id=41219
$ echo "parent id: $(ps -o ppid= ${my_child_id})"
parent id:   1
```