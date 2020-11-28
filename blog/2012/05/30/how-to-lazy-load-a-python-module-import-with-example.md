To dynamically load or lazy-load a python module, do the following:

```python
import_str = 'from pprint import pprint'
exec(import_str)
```

A more complete example with error catching.

```python
import pprint

module_name = 'bar'
definition = 'my_method'
import_str = 'from foo.{0} import {1}'.format(module_name, definition)

try:
    exec(import_str)
except ImportError:
    print('import failed:', import_str)
else:
    pprint.pprint(locals())
```

---

Posted May 30, 2012.

https://www.darklaunch.com/2012/05/30/how-to-lazy-load-a-python-module-import-with-example.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Aug 20, 2012
            <div>
                <p>That's a nice post.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Mar 14, 2015
            <div>
                <p>This looks way too easy compared to all the other solutions I've found so far ... :O</p>
            </div>
        </div>
    </li>
</ol>
