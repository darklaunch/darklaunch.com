# Python Measure Elapsed & Execution Time; Timer Class

Measure elapsed time duration using python.

```python
import time

start_time = time.time()

# Do something.
time.sleep(1.234)

end_time = time.time()
elapsed_time = end_time - start_time
```

Another way to measure multiple durations:

```python
# logging_timer.py
import logging
import time

class Timer(object):
    def __init__(self):
        self.tasks = {}
        self.level = 0
        self.task_count = 0
        self._next_task_name = ''

    def __enter__(self):
        self.level += 1
        self.task_count += 1

        if self._next_task_name:
            task_name = self._next_task_name
            self._next_task_name = ''
        else:
            task_name = 'task %s' % self.task_count

        self.tasks['entered%s' % self.level] = {
            'start_time': time.time(),
            'name': task_name,
        }
        logging.debug('        %s %s %s' % (
            self.columns(self.level - 1),
            '\u250c',
            '%s' % task_name,
            ))

    def __exit__(self, exc_type, exc_val, exc_tb):
        task = self.tasks['entered%s' % self.level]
        number = time.time() - task['start_time']
        elapsed = '{0:>5} {1}'.format(int(number * 1000), 'ms')
        logging.debug('%s%s %s %s' % (
            elapsed,
            self.columns(self.level - 1),
            '\u2514',
            '%s' % task['name'],
            ))
        self.level -= 1

    def columns(self, count):
        return ' {0} '.format('\u2502') * count

    def name(self, task_name):
        self._next_task_name = task_name
        return self
```

```python
# test.py
import logging
import time

import logging_timer

logging.getLogger().setLevel(logging.DEBUG)

timer = logging_timer.Timer()
with timer.name('Tasks'):
    with timer.name('First task'):
        time.sleep(1)

    with timer.name('Task 2'):
        with timer.name('Another task'):
            time.sleep(4)

        with timer.name('Yet another task'):
            time.sleep(.5)

            with timer.name('Do something'):
                time.sleep(3)

                with timer.name('Last task'):
                    time.sleep(.5)
```

Example run output:

```
$ python test.py
DEBUG:root:         ┌ Tasks
DEBUG:root:         │  ┌ First task
DEBUG:root: 1001 ms │  └ First task
DEBUG:root:         │  ┌ Task 2
DEBUG:root:         │  │  ┌ Another task
DEBUG:root: 4000 ms │  │  └ Another task
DEBUG:root:         │  │  ┌ Yet another task
DEBUG:root:         │  │  │  ┌ Do something
DEBUG:root:         │  │  │  │  ┌ Last task
DEBUG:root:  501 ms │  │  │  │  └ Last task
DEBUG:root: 3503 ms │  │  │  └ Do something
DEBUG:root: 4004 ms │  │  └ Yet another task
DEBUG:root: 8005 ms │  └ Task 2
DEBUG:root: 9007 ms └ Tasks
```

More tests:

```python
import logging
import time

import logging_timer

logging.getLogger().setLevel(logging.DEBUG)

timer = logging_timer.Timer()
with timer:
    time.sleep(5)
"""
        ┌ task 1 start
5000 ms └ task 1 stop
"""

timer = logging_timer.Timer()
with timer:
    time.sleep(5)

    with timer:
        time.sleep(2)
"""
        ┌ task 1 start
        │  ┌ task 2 start
2000 ms │  └ task 2 stop
7000 ms └ task 1 stop
"""

timer = logging_timer.Timer()
with timer:
    time.sleep(5)

    with timer:
        time.sleep(2)

    with timer:
        time.sleep(1)
"""
        ┌ task 1 start
        │  ┌ task 2 start
2000 ms │  └ task 2 stop
        │  ┌ task 3 start
1000 ms │  └ task 3 stop
8000 ms └ task 1 stop
"""

timer = logging_timer.Timer()
with timer:
    time.sleep(5)

    with timer:
        time.sleep(2)

        with timer:
            time.sleep(1)

    with timer:
        time.sleep(1)
"""
        ┌ task 1 start
        │  ┌ task 2 start
        │  │  ┌ task 3 start
1000 ms │  │  └ task 3 stop
3000 ms │  └ task 2 stop
        │  ┌ task 4 start
1000 ms │  └ task 4 stop
9000 ms └ task 1 stop
"""

timer = logging_timer.Timer()
with timer.name('My Task A'):
    time.sleep(5)
"""
        ┌ My Task A start
5000 ms └ My Task A stop
"""

timer = logging_timer.Timer()
with timer.name('My Task B'):
    time.sleep(5)

    with timer:
        time.sleep(2)
"""
        ┌ My Task B start
        │  ┌ task 2 start
2000 ms │  └ task 2 stop
7000 ms └ My Task B stop
"""

timer = logging_timer.Timer()
with timer.name('My Task C'):
    time.sleep(5)

    with timer:
        time.sleep(2)

    with timer:
        time.sleep(1)
"""
        ┌ My Task C start
        │  ┌ task 2 start
2000 ms │  └ task 2 stop
        │  ┌ task 3 start
1000 ms │  └ task 3 stop
8000 ms └ My Task C stop
"""

timer = logging_timer.Timer()
with timer.name('My Task D'):
    time.sleep(5)

    with timer:
        time.sleep(2)

        with timer:
            time.sleep(1)

    with timer:
        time.sleep(1)
"""
        ┌ My Task D start
        │  ┌ task 2 start
        │  │  ┌ task 3 start
1000 ms │  │  └ task 3 stop
3000 ms │  └ task 2 stop
        │  ┌ task 4 start
1000 ms │  └ task 4 stop
9000 ms └ My Task D stop
"""

timer = logging_timer.Timer()
with timer.name('My Task E'):
    time.sleep(5)

    with timer.name('Another task'):
        time.sleep(2)
"""
        ┌ My Task E start
        │  ┌ Another task start
2000 ms │  └ Another task stop
7000 ms └ My Task E stop
"""

timer = logging_timer.Timer()
with timer.name('My Task F'):
    time.sleep(5)

    with timer.name('Another task'):
        time.sleep(2)

    with timer:
        time.sleep(1)
"""
        ┌ My Task F start
        │  ┌ Another task start
2000 ms │  └ Another task stop
        │  ┌ task 3 start
1000 ms │  └ task 3 stop
8000 ms └ My Task F stop
"""

timer = logging_timer.Timer()
with timer.name('My Task G'):
    time.sleep(5)

    with timer:
        time.sleep(2)

    with timer.name('Another task'):
        time.sleep(1)
"""
        ┌ My Task G start
        │  ┌ task 2 start
2000 ms │  └ task 2 stop
        │  ┌ Another task start
1000 ms │  └ Another task stop
8000 ms └ My Task G stop
"""

timer = logging_timer.Timer()
with timer.name('My Task H'):
    time.sleep(5)

    with timer:
        time.sleep(2)

        with timer.name('Inner task'):
            time.sleep(1)

    with timer:
        time.sleep(1)
"""
        ┌ My Task H start
        │  ┌ task 2 start
        │  │  ┌ Inner task start
1000 ms │  │  └ Inner task stop
3000 ms │  └ task 2 stop
        │  ┌ task 4 start
1000 ms │  └ task 4 stop
9000 ms └ My Task H stop
"""

timer = logging_timer.Timer()
with timer.name('My Task I'):
    time.sleep(5)

    with timer:
        time.sleep(2)

        with timer.name('Inner task'):
            time.sleep(1)

    with timer.name('Last task'):
        time.sleep(1)
"""
        ┌ My Task I start
        │  ┌ task 2 start
        │  │  ┌ Inner task start
1000 ms │  │  └ Inner task stop
3000 ms │  └ task 2 stop
        │  ┌ Last task start
1000 ms │  └ Last task stop
9000 ms └ My Task I stop
"""
```

---

Posted Sep 14, 2012.

https://www.darklaunch.com/2012/09/14/python-measure-elapsed-execution-time-timer-class.html