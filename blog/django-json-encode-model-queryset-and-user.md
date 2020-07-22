Encode Django model, queryset, and user in json. Fixes:

* TypeError: &lt;Model: Model object> is not JSON serializable
* TypeError: &lt;QuerySet []> is not JSON serializable
* TypeError: &lt;User: username> is not JSON serializable

```python
import json

from django.core import serializers
from django.core.serializers.json import DjangoJSONEncoder
from django.db import models
from django.db.models.query import QuerySet
from django.forms.models import model_to_dict

class JsonEncoder(DjangoJSONEncoder):

    def default(self, obj):
        if isinstance(obj, models.Model):
            return model_to_dict(obj)
        if isinstance(obj, QuerySet):
            return serializers.serialize('python', obj, ensure_ascii=False)
        return super(JsonEncoder, self).default(obj)

def json_encode(data):
    return json.dumps(data, cls=JsonEncoder, indent=2, separators=(',', ': '))
```

```python
>>> import datetime
>>> from django.contrib.auth.models import User
>>> print(json_encode(User.objects.create(username='alice')))
{
  "username": "alice",
  "first_name": "",
  "last_name": "",
  "is_active": true,
  "email": "",
  "is_superuser": false,
  "is_staff": false,
  "last_login": null,
  "groups": [],
  "user_permissions": [],
  "password": "",
  "id": 1,
  "date_joined": "2017-04-20T00:00:00.000Z"
}
>>> print(json_encode(User.objects.all()))
[
  {
    "model": "auth.user",
    "pk": 1,
    "fields": {
      "password": "",
      "last_login": null,
      "is_superuser": false,
      "username": "alice",
      "first_name": "",
      "last_name": "",
      "email": "",
      "is_staff": false,
      "is_active": true,
      "date_joined": "2017-04-20T00:00:00.000Z",
      "groups": [],
      "user_permissions": []
    }
  }
]
```