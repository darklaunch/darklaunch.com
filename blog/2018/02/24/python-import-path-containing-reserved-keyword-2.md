Import a module from a path that contains a reserved Python keyword like "is". This fixes SyntaxError.
```python
$ python
>>> from some.path.that.contains.is.keyword import somemodule
  File "<stdin>", line 1
    from some.path.that.contains.is.keyword import somemodule
                                  ^
SyntaxError: invalid syntax
>>> 
```
Use importlib to avoid SyntaxError.
```python
$ python
>>> import importlib
>>> mymodule = importlib.import_module('some.path.that.contains.is.keyword.mymodule')
>>> mymodule
<module 'some.path.that.contains.is.keyword.mymodule' from 'some/path/that/contains/is/keyword/mymodule.pyc'>
```