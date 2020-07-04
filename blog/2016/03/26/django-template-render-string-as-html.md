Render a template filename with context to an html string in Django.

```python
from django.template.loader import render_to_string
html = render_to_string('relative/path/to/my_template.html', {'foo': 'bar'})
```

Render template from a string.

```python
>>> from django.template import Context
>>> from django.template import Template
>>> template = Template('Hello, {{ thing }}!')

>>> context = Context({'thing': 'World'})
>>> template.render(context)
u'Hello, World!'

>>> context = Context({'thing': 'Internet'})
>>> template.render(context)
u'Hello, Internet!'
```

Render template from a string with the request context available for use.

```python
# myapp/views.py
from django.http import HttpResponse
from django.template import RequestContext
from django.template import Template


def index(request):
    template = Template('Hello, {{ thing }} and {{ request.user }}!')
    context = RequestContext(request, {
        'thing': 'World',
    })
    return HttpResponse(template.render(context))
```

Response:

```
Hello, World and alice!
```