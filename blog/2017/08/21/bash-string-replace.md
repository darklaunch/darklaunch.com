Bash replace first substring match or all substring matches.

```bash
$ cat test.sh
find="b"
replace="B"
in="abcabc"

echo "find: ${find}"
echo "replace: ${replace}"
echo "in: ${in}"

echo "${in/$find/$replace}"
echo "${in//$find/$replace}"

$ bash test.sh
find: b
replace: B
in: abcabc
aBcabc
aBcaBc
```

---

Posted Aug 21, 2017.
https://www.darklaunch.com/2017/08/21/bash-string-replace