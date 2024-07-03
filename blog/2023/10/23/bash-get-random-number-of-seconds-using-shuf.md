# Bash get random number of seconds using shuf

Get a random number of seconds 1-60 in bash:

```bash
#!/usr/bin/env bash

set -x
random_seconds="$(shuf --input-range=1-60 --head-count=1)"
echo "random_seconds: ${random_seconds}"
```

```
++ shuf --input-range=1-60 --head-count=1
+ random_seconds=37
+ echo 'random_seconds: 37'
random_seconds: 37
```

---

Posted Oct 23, 2023.

https://www.darklaunch.com/2023/10/23/bash-get-random-number-of-seconds-using-shuf.html