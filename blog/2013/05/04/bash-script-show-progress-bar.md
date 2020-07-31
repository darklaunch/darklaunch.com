To show a bash script progress while loading:

```sh
#!/bin/bash

function loading {
    char="|"
    while :; do
        case "$char" in
            "|")
                char="/"
                ;;
            "/")
                char="-"
                ;;
            "-")
                char="\\"
                ;;
            "\\")
                char="|"
                ;;
        esac
        sleep .2s
        echo -en "\rLoading $char"
    done
}

loading &
pid=$!

# do something
sleep 5s

kill -9 $pid
wait $pid 2>/dev/null # Supress "Killed" message
echo -en "\r\033[K" # Completely overwrite last line

echo "Done."
```

---

Posted May 4, 2013.

https://www.darklaunch.com/2013/05/04/bash-script-show-progress-bar.html