<p>To run a multiline python script in a bash shell script from the command line, do the following:</p>

<code name="sh">
python - <<EOF
import random
print(random.random())
EOF
</code>

<p>Using cat:</p>

<code name="sh">
cat <<EOF | python -
import random
print(random.random())
EOF
</code>

<p>Pass bash variable to python script through stdin:</p>

<code name="sh">
some_bash_var="world"

script="
import sys
name = sys.stdin.read().rstrip()
print('hello ' + name)
"
echo "${some_bash_var}" | python -c "${script}"
</code>

<p>Output:</p>

<code name="sh">
$ some_bash_var="world"
$ script="
→ import sys
→ name = sys.stdin.read().rstrip()
→ print('hello ' + name)
→ "
$ echo "${some_bash_var}" | python -c "${script}"
hello world
</code>