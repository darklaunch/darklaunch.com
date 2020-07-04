<p>To fix the adb "device not found" error, 1) ensure USB debugging is enabled, 2) ensure your device is unlocked, and 3) try restarting the server.</p>

<code>
$ ./adb kill-server
$ ./adb start-server
</code>

<p>Then run a command to test communication. For example, the devices command to list all connected devices.</p>
<code>
$ ./adb devices
</code>