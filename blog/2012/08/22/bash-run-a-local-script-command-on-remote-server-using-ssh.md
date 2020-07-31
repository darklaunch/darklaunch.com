Use ssh to run a local bash script on a remote computer.

Use the following syntax:

```bash
ssh user@host sh < myscript.sh
ssh user@host bash < myscript.sh
```

If using bash, include "#!/bin/bash" at the top of myscript.sh and be sure to call `bash` instead of `sh` or you may get commands not found.

---

Posted Aug 22, 2012.

https://www.darklaunch.com/2012/08/22/bash-run-a-local-script-command-on-remote-server-using-ssh.html