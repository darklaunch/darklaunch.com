# Bash function alias to repeat arbitrary command

Add a function that allows repeatedly running the command that follows.

Example:

```bash
$ repeat date --utc
```

Output:

```
###########################################################################################################

running `date --utc`
Wed Jul 20 00:00:03 UTC 2021

###########################################################################################################

running `date --utc`
Wed Jul 20 00:00:04 UTC 2021

###########################################################################################################

running `date --utc`
Wed Jul 20 00:00:05 UTC 2021
^C
```

```bash
_repeat() {
  command_with_args_to_repeatedly_do="${@}"

  while :; do
    # Recalculate the number of columns each iteration as screen may have been resized.
    cols="$(tput cols)"
    echo
    printf -- '#%.0s' $(seq 1 $cols)
    echo
    echo

    echo "running \`$command_with_args_to_repeatedly_do'"
    $command_with_args_to_repeatedly_do

    sleep 1
  done
}
alias repeat="_repeat"
```

---

Posted Jul 20, 2021.

https://www.darklaunch.com/2021/07/20/bash-function-alias-to-repeat-arbitrary-command.html