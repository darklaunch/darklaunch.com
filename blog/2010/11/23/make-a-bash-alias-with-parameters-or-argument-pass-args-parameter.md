# Make a bash alias with parameters or argument; pass args, parameter

Bash aliases do not accept parameters. Thus, we need to change aliases that use parameters into functions.

```sh
cd() {
    builtin cd $1
    pwd
}
```

Now you can call cd(): cd /path/to/some/dir/ and cd will change to the directory and pwd will print name of current/working directory.

Using parameters as required:

```sh
findpy() {
    find . -name '*.py' -exec grep --line-number --with-filename --recursive "$1" {} \; ;
}
```

```sh
# handy extract
extract() {
    if [ -f $1 ] ; then
        case $1 in
            *.tar.bz2)   tar xvjf $1     ;;
            *.tar.gz)    tar xvzf $1     ;;
            *.bz2)       bunzip2 $1      ;;
            *.rar)       unrar x $1      ;;
            *.gz)        gunzip $1       ;;
            *.tar)       tar xvf $1      ;;
            *.tbz2)      tar xvjf $1     ;;
            *.tgz)       tar xvzf $1     ;;
            *.zip)       unzip $1        ;;
            *.Z)         uncompress $1   ;;
            *.7z)        7z x $1         ;;
            *)           echo "'$1' cannot be extracted via >extract<" ;;
        esac
    else
        echo "'$1' is not a valid file"
    fi
}
```

```sh
# mkdir, cd into it
mkcd () {
    mkdir -p "\$*"
    cd "\$*"
}
```

NOTE: use `$@` to pass the full parameter. instead of `alias foo="somecommand $1 $2 $3 $4 $5 $6"`, use `alias foo="somecommand $@"` without quotes around `$@`.

---

Posted Nov 23, 2010.

https://www.darklaunch.com/2010/11/23/make-a-bash-alias-with-parameters-or-argument-pass-args-parameter.html

---

1 comment

<ol><li><div>

anonymous &ndash; May 19, 2011<div>

Thank you sir!

</div></div></li></ol>