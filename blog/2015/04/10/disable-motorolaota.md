<p>If for whatever reason you want to disable the Motorola OTA update on Android, do the following:</p>

<code>
$ ./adb shell
shell@ghost:/ $ su
root@ghost:/ # pm disable com.motorola.ccc.ota
Package com.motorola.ccc.ota new state: disabled</code>

<p>This will disable the "Motorola Update Services".</p>

https://play.google.com/store/apps/details?id=com.motorola.ccc.ota

<p>Yes, root is required.</p>