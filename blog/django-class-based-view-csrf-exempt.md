Example of Django CSRF exempt class based views.

Bypasses "HTTP/1.0 403 Forbidden", "Forbidden (CSRF cookie not set.)", "Forbidden (403) CSRF verification failed. Request aborted."

```python
from django.http import HttpResponse
from django.utils.decorators import method_decorator
from django.views import View
from django.views.decorators.csrf import csrf_exempt

@method_decorator(csrf_exempt, name='dispatch')
class MyCsrfExemptView(View):

    def post(self, request):
        return HttpResponse('OK')
```

NOTE: This can be unsafe. Consider using Access-Control-Allow-Origin or verifying the origin header and the referer header.