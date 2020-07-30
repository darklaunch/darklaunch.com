Automatically move your mouse to keep your screen from locking.

Ubuntu
```sh
while :; do
  xdotool mousemove_relative -- 1 0
  sleep 1
  xdotool mousemove_relative -- -1 0
  sleep 60
done
```

OS X
```sh
timeout=$((10 * 60))
while :; do
  last_mouse_position=$(cliclick "p")

  sec="${timeout}"
  while [[ $sec -ge 0 ]]; do
    echo -ne "\r$sec\033[0K"
    sec=$((sec-1))
    sleep 1
  done
  echo -ne "\r"

  current_mouse_position=$(cliclick "p")
  if [[ $last_mouse_position == $current_mouse_position ]]; then
      cliclick "m:+1,+0"
      cliclick "m:-1,+0"
  fi
done
```

---

Posted May 13, 2015.
https://www.darklaunch.com/2015/05/13/move-mouse-to-prevent-screensaver-from-activating-locking