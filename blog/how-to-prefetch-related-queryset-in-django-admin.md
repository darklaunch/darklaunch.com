Use prefetch_related and select_related in Django admin. Implement a custom get_queryset method.
```py
from django.contrib import admin

class MyModelAdmin(admin.ModelAdmin):
  def get_queryset(self, request):
    queryset = super(MyModelAdmin, self).get_queryset(request)
    queryset = queryset.prefetch_related('user')
    return queryset
```