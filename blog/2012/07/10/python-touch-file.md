# Python touch file

To touch a file in python, do the following:

```python
import os

def touch(fname, times=None):
    """
    touch - change file timestamps
    """
    with file(fname, 'wa'):
        os.utime(fname, times)

if __name__ == '__main__':
    for i in range(0, 10):
        filename = 'somefile{i}.txt'.format(i=i)
        print(filename)
        touch(filename)
```

<img alt="" src="/img/uploads/2012-07/python-touch-file.png" />

---

Posted Jul 10, 2012.

https://www.darklaunch.com/2012/07/10/python-touch-file.html