The error:
```
X Error of failed request:  XF86VidModeExtensionDisabled
  Major opcode of failed request:  129 (XFree86-VidModeExtension)
  Minor opcode of failed request:  6 (XF86VidModeGetAllModeLines)
  Serial number of failed request:  88
  Current serial number in output stream:  88
```

To fix, add "UseXVidMode" key to ~/.wine/user.reg
```sh
cat >>"$HOME/.wine/user.reg" &lt;&lt;EOF

[Software\\\\Wine\\\\X11 Driver] 1269299093
"UseXVidMode"="N"
EOF
```

Wine should now load.

---

Posted Sep 20, 2010.

https://www.darklaunch.com/2010/09/20/wine-fails-with-x-error-of-failed-request-xf86vidmodeextensiondisabled-usexvidmode.html