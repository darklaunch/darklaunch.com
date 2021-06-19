# Django Fix "AttributeError: This QueryDict instance is immutable"

Fix the Django error: "AttributeError: This QueryDict instance is immutable".

```python
from django.contrib.admin.sites import AdminSite

def my_view(request):
    admin_site = admin.MyModelAdmin(models.MyModel, AdminSite())
    request.GET._mutable = True
    request.GET['_popup'] = '1'
    request.GET._mutable = False
    return admin_site.add_view(request)
```

---

Posted Oct 12, 2014.

https://www.darklaunch.com/2014/10/12/django-fix-attributeerror-this-querydict-instance-is-immutable.html