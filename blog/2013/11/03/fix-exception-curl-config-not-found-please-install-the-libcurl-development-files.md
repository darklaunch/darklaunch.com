Fix the Exception error that `curl-config' is not found. Do the following to fix:
```
$ sudo apt-get install python2.7-dev
$ sudo apt-get install libcurl4-openssl-dev
```

Now you can continue with the pycurl install
```
$ pip install pycurl
```