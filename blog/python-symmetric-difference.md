Find if there are elements not common to both sets.

```python
def symmetric_difference(iter_1, iter_2):
    """Return True when either parameter contains elements not in both."""
    return True if len(set(iter_1) ^ set(iter_2)) else False
```

```python
print(symmetric_difference(['a'], ['a'])) # False
print(symmetric_difference(['a', 'b'], ['a', 'b'])) # False
print(symmetric_difference(['a', 'b', 'c'], ['a', 'b'])) # True
print(symmetric_difference(['a', 'b'], ['a', 'b', 'c'])) # True
```