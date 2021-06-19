# Fix Exception: `curl-config' not found - please install the libcurl development files

Fix the Exception error that `curl-config` is not found. Do the following to fix:

```bash
$ sudo apt-get install python2.7-dev
$ sudo apt-get install libcurl4-openssl-dev
```

Now you can continue with the pycurl install

```bash
$ pip install pycurl
```

---

Posted Nov 3, 2013.

https://www.darklaunch.com/2013/11/03/fix-exception-curl-config-not-found-please-install-the-libcurl-development-files.html