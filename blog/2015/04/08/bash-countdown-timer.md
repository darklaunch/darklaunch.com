Create a countdown timer in bash. This will display a timer and countdown the number of seconds.

```bash
sec=3
while [[ $sec -gt 0 ]]; do
  echo -ne "\r$sec\033[0K"
  sec=$((sec-1))
  sleep 1
done
echo -ne "\r"
```

---

Posted Apr 8, 2015.

https://www.darklaunch.com/2015/04/08/bash-countdown-timer.html