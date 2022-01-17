# Run functions in split windows with tmux

Run functions in split windows using tmux (or byobu) by using the `tmux split-window` command.

```bash
run_function_one() {
    echo "this is function #1"
    date
    sleep 5
}

run_function_two() {
    echo "this is function #2"
    date
    echo "function #2 done"
}

# Run the first function in a new window. The window will self-close when the
# function commands have completed.
function_one="$(type run_function_one | head --lines=-1 | tail --lines=+4)"
tmux split-window "${function_one}"

# Run the second function in this window.
run_function_two
```

---

Posted Jan 16, 2022.

https://www.darklaunch.com/2022/01/16/run-functions-in-split-windows-with-tmux.html