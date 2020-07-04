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
? import sys
? name = sys.stdin.read().rstrip()
? print('hello ' + name)
? "
$ echo "${some_bash_var}" | python -c "${script}"
hello world
```