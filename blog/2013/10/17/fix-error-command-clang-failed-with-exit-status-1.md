<img alt="" src="/img/uploads/2013-10/xcode-install-command-line-tools.png" />

To fix error: command 'clang' failed with exit status 1 when running `pip install pycurl', install Command Line Tools from Xcode.

<ol>
    <li>Open Xcode</li>
    <li>Go to Preferences (Command + ,)</li>
    <li>Select the Downloads tab / Components subtab</li>
    <li>Install Command Line Tools</li>
</ol>

Then pip install with ARCHFLAGS set:

```$ env ARCHFLAGS="-arch x86_64" pip install pycurl```