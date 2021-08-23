# Django call class based view in script

Call a Django view with query parameters using querydict in a python script.

A simple view we want to call from a script:

```python
from django.http import HttpResponse
from django.utils import timezone
from django.views import View

class MyView(View):
    def get(self, request):
        now = timezone.now()
        html = "<html><body>It is now %s.</body></html>" % now
        return HttpResponse(html)
```

The script where we call the class-based view:

```python
from django.contrib.auth.models import User
from django.http import HttpRequest
from django.http.request import QueryDict

from myapp.views import MyView

user = User.objects.get(username='admin')

get = QueryDict('defer=0&id=1234&force')

request = HttpRequest()
request.method = 'GET'
request.user = user
request.GET = get

result = MyView.as_view()(request)
print('result:')
print(result)
```

The output when the script is run:

```
result:
Content-Type: text/html; charset=utf-8

<html><body>It is now 2018-05-15 00:00:00.000000+00:00.</body></html>
```

Pass additional arguments to the view.

```python
from django.http import HttpResponse
from django.views import View

class MyBlogView(View):
    def get(self, request, page_number=None):
        if not page_number:
            page = 1
        html = "<html><body>You are on page %s.</body></html>" % page_number
        return HttpResponse(html)
```

```python
from django.http import HttpRequest

from myapp.views import MyBlogView

request = HttpRequest()
request.method = 'GET'

page_number = 2
result = MyBlogView.as_view()(request, page_number)
print('result:')
print(result)
```

```
result:
Content-Type: text/html; charset=utf-8

<html><body>You are on page 2.</body></html>
```

---

Posted May 15, 2018.

https://www.darklaunch.com/2018/05/15/django-call-class-based-view-in-script.html

---

1 comment

<ol><li><div>

Avramo &ndash; Jul 21, 2021<div>

I was looking for this for hours,
Great post, super clear and easy!
Thanks!

</div></div></li></ol>