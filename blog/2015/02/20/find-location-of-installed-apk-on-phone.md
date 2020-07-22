How to find the apk file location in Android device and download/pull/save it.

```
./adb shell pm list packages -f
./adb pull /data/app/com.company.project.apps.appname.apk .
./adb install com.company.project.apps.appname.apk .
```