<p>Import a module from a path containing a reserved keyword like "is".</p>

<p>This import statement fails because the word "is" is a reserved in python.</p>
<code name="python">
from foo.com.example.is.path.somewhere.api.v1 import resources
</code>

<p>Use importlib to import.</p>
<code name="python">
import importlib

mymodule = importlib.import_module('foo.com.example.is.path.somewhere.api.v1.resources')
</code>