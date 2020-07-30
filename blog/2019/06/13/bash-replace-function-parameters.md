Shift and unshift a bash function's parameters by creating a new variable to hold the arguments passed to the function.

```bash
debug_command() {
    echo "  arg 1: ${args[0]}"
    echo "  arg 2: ${args[1]}"
    echo "  arg 3: ${args[2]}"
}

my_func() {
    args=("${@}")

    echo "original args:"
    debug_command "${args[@]}"

    # Replace first argument (at index 0).
    args[0]="changed!"

    echo "modified args:"
    debug_command "${args[@]}"
}

my_func "first" "2nd" "and third"
```

```
$ bash replace_func_arg.sh
original args:
  arg 1: first
  arg 2: 2nd
  arg 3: and third
modified args:
  arg 1: changed!
  arg 2: 2nd
  arg 3: and third
```

kw: bash, shift, unshift

---

Posted Jun 13, 2019.
https://www.darklaunch.com/2019/06/13/bash-replace-function-parameters