To run a multiline python script in a bash shell script from the command line, do the following:

```sh
python - <<EOF
import random
print(random.random())
EOF
```

Using cat:

```sh
cat <<EOF | python -
import random
print(random.random())
EOF
```

Pass bash variable to python script through stdin:

```sh
some_bash_var="world"

script="
import sys
name = sys.stdin.read().rstrip()
print('hello ' + name)
"
echo "${some_bash_var}" | python -c "${script}"
```

Output:

```sh
$ some_bash_var="world"
$ script="
→ import sys
→ name = sys.stdin.read().rstrip()
→ print('hello ' + name)
→ "
$ echo "${some_bash_var}" | python -c "${script}"
hello world
```

---

Posted Feb 3, 2012.

https://www.darklaunch.com/2012/02/03/how-to-include-python-script-in-bash-script.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Feb 22, 2012
            <div>
Alternatively, something like this works as well:

eval python - &lt;&lt; EOF
import sys
from pprint import pprint
pprint(sys.path)
EOF
            </div>
        </div>
    </li>
</ol>
