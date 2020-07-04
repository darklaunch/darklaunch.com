<p>Capture stdout output in python using a context manager.</p>

<code name="python">
import cStringIO
import sys


class CaptureOutput(list):
    def __enter__(self):
        self._stdout = sys.stdout
        sys.stdout = self._stringio = cStringIO.StringIO()
        return self

    def __exit__(self, *args):
        self.extend(self._stringio.getvalue().splitlines())
        del self._stringio
        sys.stdout = self._stdout
</code>

<p>Usage:</p>

<code name="python">
def count_to_3():
    for i in range(1, 4):
        print(i)

with CaptureOutput() as lines:
    count_to_3()

print('done counting')

for line in lines:
    print('line: %s' % line)
</code>

<p>Output:</p>

<code>
done counting
line: 1
line: 2
line: 3
</code>

<p>Capture stdout output in php.</p>

<code name="php">
<?php
function count_to_3() {
    for ($i = 1; $i <= 3; $i++) {
        echo $i . "\n";
    }
}

ob_start();
count_to_3();
$lines = explode("\n", rtrim(ob_get_contents()));
ob_end_clean();

echo 'done counting' . "\n";

foreach ($lines as $line) {
    echo 'line: ' . $line . "\n";
}
</code>

<p>Output:</p>

<code>
done counting
line: 1
line: 2
line: 3
</code>

https://stackoverflow.com/questions/16571150/