Fix TypeError: datetime.datetime is not JSON serializable error.

```python
import datetime
import json

from django.core.serializers.json import DjangoJSONEncoder


print json.dumps({
    'timestamp': datetime.datetime.now(),
}, cls=DjangoJSONEncoder, indent=2)
```