Firefox allows changing the default view source editor.

Open Firefox and enter `about:config` into the url bar.

On this preferences page, change the following:

```
view_source.editor.external=true;
view_source.editor.path=/usr/bin/scite;
```