Call `all()` on a previously evaluated QuerySet to get updated results.

```python
from myapp.models import Question

q1 = Question.objects.create(question_text='Who am I?')
q2 = Question.objects.create(question_text='Where did I come from?')
q3 = Question.objects.create(question_text='Why am I here?')

questions = Question.objects.all()

if questions:
    print('questions found') # <-- HERE
else:
    print('questions not found')

q1.delete()
q2.delete()
q3.delete()

if questions:
    print('questions still found') # <-- HERE
else:
    print('questions not found')

# Call all() on a previously evaluated QuerySet to get the updated results.
if questions.all():
    print('questions still found')
else:
    print('questions not found') # <-- HERE
```

Output:

```
questions found
questions still found
questions not found
```

Alternatively, manually clear the `QuerySet` results cache.

```python
my_queryset._result_cache = None
my_queryset.count()
```

For an individual object, use `refresh_from_db()`.

```python
obj = MyModel.objects.get(pk=1)
obj.refresh_from_db()
```

---

Posted May 14, 2017.

https://www.darklaunch.com/2017/05/14/django-refresh-queryset-count.html