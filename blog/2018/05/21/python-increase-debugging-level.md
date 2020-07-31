By default, python will only display warnings, errors, and critical messages. Change the debugging level to display all logging messages.

Change the logging level threshold by using setLevel().

```python
import logging

logging.getLogger().setLevel(logging.DEBUG)

logging.debug('debug message')
logging.info('info message')
logging.warning('warning message')
logging.error('error message')
logging.critical('critical message')
```

---


Posted May 21, 2018.
https://www.darklaunch.com/2018/05/21/python-increase-debugging-level.html