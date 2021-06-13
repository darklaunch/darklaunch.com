Watch a file for file modifications and run a command. For known file extensions, the script may run itself. For all other extensions, specify a command to run.

Usage:

```bash
$ watch_file path/to/script.py
$ wf script.py "python script.py"
$ wf script.py
$ wf script.py "bash run.sh"
$ wf page.html "open https://www.example.com/"
```

```bash
watch_file ()
{
    filename="${1}";
    cmd="${2}";
    cols=$(tput cols);
    if [[ "${OSTYPE}" == "linux-gnu" ]]; then
        python_script=$(cat <<'EOF'
import os
import pipes
import sys

filename = sys.argv[1]
_, file_extension = os.path.splitext(filename)
filepath = os.path.abspath(filename)
cmd = sys.argv[2]
if not cmd:
    if file_extension == '.js':
        cmd = 'node {0}'.format(pipes.quote(filename))
    elif file_extension == '.php':
        cmd = 'php {0}'.format(pipes.quote(filename))
    elif file_extension == '.py':
        cmd = 'python {0}'.format(pipes.quote(filename))
    elif file_extension == '.sh':
        cmd = 'bash {0}'.format(pipes.quote(filename))
print(cmd)
EOF
);
        cmd=$(python -c "${python_script}" "${filename}" "${cmd}");
        echo;
        while inotifywait --event modify --quiet "${filename}"; do
            printf -- '-=%.0s' $(eval echo {1.."${cols}"});
            echo;
            if [ ! -z "${cmd}" ]; then
                bash -c "${cmd}";
            fi;
        done;
    else
        if [[ "${OSTYPE}" == "darwin"* ]]; then
            echo -e '\x1b[0;93mWARNING\x1b[0m: watch using polling';
            python_script=$(cat <<'EOF'
import math
import os
import pipes
import random
import shlex
import subprocess
import sys
import time

cols = int(sys.stdin.read().rstrip())
separator = '-=' * int(math.floor(cols / 2))

filename = sys.argv[1]
_, file_extension = os.path.splitext(filename)
filepath = os.path.abspath(filename)
cmd = sys.argv[2]
if not cmd:
    if file_extension == '.js':
        cmd = 'node {0}'.format(pipes.quote(filename))
    elif file_extension == '.php':
        cmd = 'php {0}'.format(pipes.quote(filename))
    elif file_extension == '.py':
        cmd = 'python {0}'.format(pipes.quote(filename))
    elif file_extension == '.sh':
        cmd = 'bash {0}'.format(pipes.quote(filename))
cmd_parts = shlex.split(cmd)
print(cmd)

last = cur = os.path.getmtime(filepath)
while True:
    time.sleep(1)
    try:
        cur = os.path.getmtime(filepath)
        if cur != last:
            last = cur
            print(separator)
            proc = subprocess.Popen(cmd_parts)
            proc.communicate()[0]
            print('return code: %s' % proc.returncode)
            print
            time.sleep(1)
            print(random.random())
    except OSError as e:
        print('failed to get file modification time (%s)' % e.message)
EOF
);
            echo "${cols}" | python -c "${python_script}" "${filename}" "${cmd}";
        fi;
    fi
}

alias wf="watch_file"
```

Part of https://github.com/dot-star/dot-star

---

Posted Mar 15, 2018.

https://www.darklaunch.com/2018/03/15/watch-file-for-changes-and-run-command.html

---

1 comment

<ol><li><div>

anonymous &ndash; Aug 24, 2019<div>

See also https://www.darklaunch.com/watch-files-and-run-a-command

</div></div></li></ol>