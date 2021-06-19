# Bash require run as root

Require a bash script to run with root permissions.

```sh
#!/bin/bash

if [[ "${EUID}" != 0 ]]; then
   echo "Script must be run as root. Try: sudo bash ${0}"
   exit 1
fi
```

---

Posted Dec 8, 2016.

https://www.darklaunch.com/2016/12/08/bash-require-run-as-root.html