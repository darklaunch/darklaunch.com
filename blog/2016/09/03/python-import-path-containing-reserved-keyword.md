# Python import path containing reserved keyword

Import a module from a path containing a reserved keyword like `is`.

This import statement fails because the word `is` is a reserved in python.

```python
from foo.com.example.is.path.somewhere.api.v1 import resources
```

Use `importlib` to import.

```python
import importlib

mymodule = importlib.import_module('foo.com.example.is.path.somewhere.api.v1.resources')
```

---

Posted Sep 3, 2016.

https://www.darklaunch.com/2016/09/03/python-import-path-containing-reserved-keyword.html