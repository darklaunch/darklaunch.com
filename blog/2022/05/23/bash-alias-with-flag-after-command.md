# Bash alias that adds flag after the specified command

Add a flag after the specified command using a function. This example adds the flags`--debug` and `--verbose` after all `brew` commands:

```sh
# Increase verbosity of brew commands. Useful for seeing some progress when
# calling `brew update' on a slower connection.
#
# Call:
#   $ brew update
# Call runs:
#   $ brew update --debug --verbose
_brew() {
    set -x
    /usr/local/bin/brew $@ --debug --verbose
    set +x
}
alias brew="_brew"
```

---

Posted May 23, 2022.

https://www.darklaunch.com/2022/05/23/bash-alias-with-flag-after-command.html