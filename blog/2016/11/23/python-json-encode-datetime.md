Fix TypeError: datetime.datetime is not JSON serializable error.

```python
import datetime
import json

from django.core.serializers.json import DjangoJSONEncoder

print json.dumps({
    'timestamp': datetime.datetime.now(),
}, cls=DjangoJSONEncoder, indent=2)
```

---

Posted Nov 23, 2016.
https://www.darklaunch.com/2016/11/23/python-json-encode-datetime