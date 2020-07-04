<p>Render a template filename with context to an html string in Django.</p>

<code name="python">
from django.template.loader import render_to_string
html = render_to_string('relative/path/to/my_template.html', {'foo': 'bar'})
</code>

<p>Render template from a string.</p>

<code name="python">
>>> from django.template import Context
>>> from django.template import Template
>>> template = Template('Hello, {{ thing }}!')

>>> context = Context({'thing': 'World'})
>>> template.render(context)
u'Hello, World!'

>>> context = Context({'thing': 'Internet'})
>>> template.render(context)
u'Hello, Internet!'
</code>

<p>Render template from a string with the request context available for use.</p>

<code name="python">
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
</code>

<p>Response:</p>

<code>
Hello, World and alice!
</code>