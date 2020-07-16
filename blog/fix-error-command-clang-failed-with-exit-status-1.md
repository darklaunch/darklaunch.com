<img alt="" src="/img/uploads/2013-10/xcode-install-command-line-tools.png" />

To fix error: command 'clang' failed with exit status 1 when running `pip install pycurl`, install Command Line Tools from Xcode.


    <li>Open Xcode
    <li>Go to Preferences (Command + ,)
    <li>Select the Downloads tab / Components subtab
    <li>Install Command Line Tools


Then pip install with ARCHFLAGS set:
```
$ env ARCHFLAGS="-arch x86_64" pip install pycurl
```