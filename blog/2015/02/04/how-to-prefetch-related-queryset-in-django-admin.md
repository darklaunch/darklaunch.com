Use prefetch_related and select_related in Django admin. Implement a custom get_queryset method.

```py
from django.contrib import admin

class MyModelAdmin(admin.ModelAdmin):
  def get_queryset(self, request):
    queryset = super(MyModelAdmin, self).get_queryset(request)
    queryset = queryset.prefetch_related('user')
    return queryset
```

---

Posted Feb 4, 2015.

https://www.darklaunch.com/2015/02/04/how-to-prefetch-related-queryset-in-django-admin.html

---

1 comment

<ol><li><div>

anonymous &ndash; Jan 12, 2016<div>

.queryset changed to .get_queryset in Django 1.6

<a href="https://docs.djangoproject.com/en/dev/ref/contrib/admin/#django.contrib.admin.ModelAdmin.get_queryset">https://docs.djangoproject.com/en/dev/ref/contrib/admin/#django.contrib.admin.ModelAdmin.get_queryset</a>

</div></div></li></ol>