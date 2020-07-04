Import a module from a path containing a reserved keyword like "is".

This import statement fails because the word "is" is a reserved in python.
```python
from foo.com.example.is.path.somewhere.api.v1 import resources
```
Use importlib to import.
```python
import importlib

mymodule = importlib.import_module('foo.com.example.is.path.somewhere.api.v1.resources')
```