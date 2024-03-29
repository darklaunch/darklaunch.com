# Run Downloaded Apps with iPhone Simulator on OS X

To run downloaded apps with the iPhone Simulator, do the following:

```
Open Finder and go to the "Applications" directory for the iPhone Simulator.
$ cd /Users/user/Library/Application Support/iPhone Simulator/5.1/Applications

Create a UUID directory.
$ mkdir 43C040CD-C419-5TCD-ACC0-8F1C36F8DF31

Copy the application to your newly created directory.
$ cd 43C040CD-C419-5TCD-ACC0-8F1C36F8DF31
$ cp ~/MyApplication.app .

Run the iPhone Simulator and your application will be displayed on one
of the screens.
$ /Applications/Xcode.app/Contents/Applications/iPhone\ Simulator.app/Contents/MacOS/iPhone\ Simulator
```

<img alt="" src="/img/uploads/2012-09/search-iphone-simulator.png" />

<img alt="" src="/img/uploads/2012-09/iphone-simulator.png" />

---

Posted Sep 11, 2012.

https://www.darklaunch.com/2012/09/11/run-downloaded-apps-with-iphone-simulator-on-os-x.html