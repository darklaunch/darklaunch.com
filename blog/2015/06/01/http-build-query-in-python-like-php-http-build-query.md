A http build query in python that is similar to php's http_build_query().

```python
import collections
import urllib

def http_build_query(data):
    dct = collections.OrderedDict()
    for key, value in data.iteritems():
        if isinstance(value, basestring):
            dct[key] = value
        elif isinstance(value, list):
            for index, v in enumerate(value):
                dct['{0}[{1}]'.format(key, index)] = v
    return urllib.urlencode(dct)
```