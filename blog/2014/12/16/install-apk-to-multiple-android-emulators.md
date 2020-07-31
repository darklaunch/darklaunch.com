```
$ ./adb install ~/my_app.apk
error: more than one device and emulator
- waiting for device -
```

Fix by installing to a specific device.

List devices
```
$ ./adb devices -l
List of devices attached 
emulator-5554          device
emulator-5556          device
```

Install to each device
```
$ ./adb -s emulator-5554 install ~/my_app.apk
$ ./adb -s emulator-5556 install ~/my_app.apk
```

Notes

Fix "can't find 'emulator-5554' to install" by using the correct syntax / parameter order.
```
$ ./adb install -s emulator-5554 ~/my_app.apk =>
$ ./adb -s emulator-5554 install ~/my_app.apk
```

---

Posted Dec 16, 2014.

https://www.darklaunch.com/2014/12/16/install-apk-to-multiple-android-emulators.html