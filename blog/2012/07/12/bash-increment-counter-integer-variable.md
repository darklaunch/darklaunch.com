# Bash Increment Counter Integer Variable

To increment a counter in bash, use any of the following:

```sh
#!/bin/bash

set -x

x=1
echo $x

(( x++ ))
echo $x

(( x += 1 ))
echo $x

let x++
echo $x

x=$(echo "$x + 1" | bc)
echo $x
```

```
+ x=1
+ echo 1
1
+ ((  x++  ))
+ echo 2
2
+ ((  x += 1  ))
+ echo 3
3
+ let x++
+ echo 4
4
++ echo '4 + 1'
++ bc
+ x=5
+ echo 5
5
```

kw: addition, add, subtraction, subtract, mathematics, math

---

Posted Jul 12, 2012.

https://www.darklaunch.com/2012/07/12/bash-increment-counter-integer-variable.html

---

2 comments

<ol><li><div>

anonymous &ndash; May 21, 2013<div>

Thanks

</div></div></li><li><div>

anonymous &ndash; Oct 24, 2013<div>

Thank you. I've only seen the `x=$((x+1))` variant. The `((x++))` is a new one for me.

</div></div></li></ol>