Django track changes to a model.
```py
# models.py
from django.contrib.auth.models import User
from django.db import models
from django.db.models import ManyToOneRel


class Person(models.Model):
    first_name = models.CharField(max_length=30)
    last_name = models.CharField(max_length=30)
    location = models.CharField(blank=True, max_length=30)
    favorite_color = models.CharField(blank=True, max_length=30)

    def __unicode__(self):
        return u'{0} {1}'.format(self.first_name, self.last_name)

    def __setattr__(self, name, value):
        super(Person, self).__setattr__(name, value)
        if name in self._meta.get_all_field_names():
            try:
                getattr(self, '_old_{0}'.format(name))
            except AttributeError:
                setattr(self, '_old_{0}'.format(name), value)

    def save(self, *args, **kwargs):
        super(Person, self).save(*args, **kwargs)

        for field_name in self._meta.get_all_field_names():
            field = self._meta.get_field(field_name)
            if not isinstance(field, ManyToOneRel):
                try:
                    old_value = getattr(self, '_old_{0}'.format(field_name))
                except AttributeError:
                    continue

                new_value = getattr(self, field_name)
                if new_value != old_value:
                    change = PersonChange()
                    change.obj = self
                    change.field_name = field_name
                    change.old_value = old_value
                    change.new_value = new_value
                    change.changed_by = self._user if hasattr(self, '_user') else None
                    change.save()


class PersonChange(models.Model):
    obj = models.ForeignKey(Person)
    field_name = models.CharField(db_index=True, max_length=255)
    old_value = models.TextField(blank=True, null=True)
    new_value = models.TextField(blank=True, null=True)
    changed_by = models.ForeignKey(User, blank=True, null=True)
    changed_at = models.DateTimeField(auto_now_add=True)
```
```py
# admin.py
from django.contrib import admin

from .models import Person
from .models import PersonChange


class PersonAdmin(admin.ModelAdmin):
    list_display = ('pk', 'first_name', 'last_name', 'location', 'favorite_color',)
    search_fields = ('id', 'first_name', 'last_name', 'location', 'favorite_color',)

    def save_model(self, request, obj, form, change):
        obj._user = request.user
        super(PersonAdmin, self).save_model(request, obj, form, change)


class PersonChangeAdmin(admin.ModelAdmin):
    list_display = ('pk', 'obj', 'field_name', 'old_value', 'new_value', 'changed_at', 'changed_by')


admin.site.register(Person, PersonAdmin)
admin.site.register(PersonChange, PersonChangeAdmin)
```