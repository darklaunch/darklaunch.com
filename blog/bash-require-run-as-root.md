Require a bash script to run with root permissions.
```sh
#!/bin/bash

if [[ "${EUID}" != 0 ]]; then
   echo "Script must be run as root. Try: sudo bash ${0}"
   exit 1
fi
```