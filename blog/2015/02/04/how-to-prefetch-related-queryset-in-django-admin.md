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
https://www.darklaunch.com/2015/02/04/how-to-prefetch-related-queryset-in-django-admin