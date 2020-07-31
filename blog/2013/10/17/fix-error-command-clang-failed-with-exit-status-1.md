<img alt="" src="/img/uploads/2013-10/xcode-install-command-line-tools.png" />

To fix error: command 'clang' failed with exit status 1 when running `pip install pycurl`, install Command Line Tools from Xcode.

* Open Xcode
* Go to Preferences (Command + ,)
* Select the Downloads tab / Components subtab
* Install Command Line Tools

Then pip install with ARCHFLAGS set:

```
$ env ARCHFLAGS="-arch x86_64" pip install pycurl
```

---

Posted Oct 17, 2013.

https://www.darklaunch.com/2013/10/17/fix-error-command-clang-failed-with-exit-status-1.html