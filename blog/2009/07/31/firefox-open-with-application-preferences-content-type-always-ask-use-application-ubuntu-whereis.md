# Firefox open with application preferences; Content Type; Always ask; Use application; Ubuntu whereis

How to set the default application for Firefox downloads:

In Firefox go to Edit > Preferences (OR Tools > Preferences).
In the new window, select Applications at the top.
Find the Content Type. For example PY file (a python script).
On right right, select "Use other..." from the drop down and browse for your application and click open; I will associate PY with geany.
Then close the Firefox Preferences window.

Now anytime a file where Content-Type=text/x-python comes up, geany will be the associated application in Firefox.

NOTE: If you don't know the location of your application, open a terminal and type:

```bash
$ whereis myapplication
```

That is:

```bash
$ whereis geany
>>> geany: /usr/bin/geany /usr/lib/geany /usr/lib64/geany /usr/include/geany /usr/share/geany /usr/share/man/man1/geany.1.gz
```

Now we know the location of geany is `/usr/bin/geany`.

---

Posted Jul 31, 2009.

https://www.darklaunch.com/2009/07/31/firefox-open-with-application-preferences-content-type-always-ask-use-application-ubuntu-whereis.html