Find variable assignments in a python file using the ast module without executing the file.

Given any of the following 3 files, we can find the value of the "VERSION" variable.

```python
VERSION = (3, 0, 0, 'alpha', 0)
```

```python
VERSION = 3.0
```

```python
VERSION = '3.0'
```

```python
from __future__ import print_function

import ast

filename = '__init__.py'
version = None
with open(filename, 'r') as source_file:
    module = ast.parse(source_file.read())
    for descendant in ast.walk(module):
        if not hasattr(descendant, 'body'):
            continue

        if not isinstance(descendant.body, list):
            continue

        for assignment in descendant.body:
            if not hasattr(assignment, 'targets'):
                continue

            target = assignment.targets[0]
            if target.id != 'VERSION':
                continue

            value_type = type(assignment.value)
            if value_type == ast.Num:
                print('number found on line number {}'.format(assignment.lineno))
                version = assignment.value.n
            elif value_type == ast.Str:
                print('string found on line number {}'.format(assignment.lineno))
                version = assignment.value.s
            elif value_type == ast.Tuple:
                print('tuple found on line number {}'.format(assignment.lineno))
                parts = []
                for element in assignment.value.elts:
                    element_type = type(element)
                    if element_type == ast.Num:
                        value = element.n
                    elif element_type == ast.Str:
                        value = element.s
                    else:
                        value = None
                    parts.append(value)
                version = tuple(parts)

print('type: {}'.format(type(version)))
print('version: {}'.format(version))
```

Output:

```bash
tuple found on line number 1
type: <type 'tuple'>
version: (3, 0, 0, 'alpha', 0)
```

```bash
number found on line number 1
type: <type 'float'>
version: 3.0
```

```bash
string found on line number 1
type: <type 'str'>
version: 3.0
```