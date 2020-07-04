<p>Bash replace first substring match or all substring matches.</p>

<code name="bash">
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
</code>