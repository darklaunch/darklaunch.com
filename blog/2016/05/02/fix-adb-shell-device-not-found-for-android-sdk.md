To fix the adb "device not found" error, 1) ensure USB debugging is enabled, 2) ensure your device is unlocked, and 3) try restarting the server.

```
$ ./adb kill-server
$ ./adb start-server
```

Then run a command to test communication. For example, the devices command to list all connected devices.
```
$ ./adb devices
```

---

Posted May 2, 2016.

https://www.darklaunch.com/2016/05/02/fix-adb-shell-device-not-found-for-android-sdk.html