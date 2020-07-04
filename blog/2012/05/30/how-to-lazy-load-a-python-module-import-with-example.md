To dynamically load or lazy-load a python module, do the following:

```python
import_str = 'from pprint import pprint'
exec import_str
```

A more complete example with error catching.

```python
module_name = 'bar'
definition = 'my_method'
import_str = 'from foo.{0} import {1}'.format(module_name, definition)

try:
    exec import_str
except ImportError:
    print 'import failed:', import_str
else:
    from pprint import pprint
    pprint(locals())
```