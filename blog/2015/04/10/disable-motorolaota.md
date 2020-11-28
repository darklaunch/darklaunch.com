If for whatever reason you want to disable the Motorola OTA update on Android, do the following:

```
$ ./adb shell
shell@ghost:/ $ su
root@ghost:/ # pm disable com.motorola.ccc.ota
Package com.motorola.ccc.ota new state: disabled
```

This will disable the "Motorola Update Services".

https://play.google.com/store/apps/details?id=com.motorola.ccc.ota

Yes, root is required.

---

Posted Apr 10, 2015.

https://www.darklaunch.com/2015/04/10/disable-motorolaota.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Apr 15, 2016
            <div>

Root required

            </div>
        </div>
    </li>
</ol>
