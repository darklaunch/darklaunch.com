FIRST to test that your webcam at least works, run
```
gstreamer-properties
```

go to the "Video" tab.
try changing the "Plugin:" setting under "Default Input"
and clicking the Test button.

mine worked with the following settings:
Plugin: Video for Linux 2 (v4l2)
Device: Default
Pipeline: v4l2src

---

NEXT, get your webcam working with Skype
```
env LD_PRELOAD=/usr/lib/libv4l/v4l1compat.so skype
```

this will open up an instance of Skype.
go to Options > Video Devices.
check "Enable Skype Video".
select your webcam and click the Test button.
if you see the webcam in the box works, your webcam will now work during calls.

---

Here are some of the errors that came up:

```
$ luvcview 
luvcview 0.2.6

SDL information:
  Video driver: x11
  A window manager is available
Device information:
  Device path:  /dev/video0
ERROR opening V4L interface: No such file or directory
```

```
$ luvcview 
luvcview 0.2.6

SDL information:
  Video driver: x11
  A window manager is available
Device information:
  Device path:  /dev/video0
Stream settings:
ERROR: Requested frame format MJPG is not available and no fallback format was found.
 Init v4L2 failed !! exit fatal
```

---

http://ubuntuforums.org/showthread.php?t=914952
http://cwraig.id.au/?p=122

---

Posted Jul 7, 2010.

https://www.darklaunch.com/2010/07/07/logitech-quickcam-communicate-stx-skype-ubuntu.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Oct 1, 2010
            <div>

also, if it still doesn't work, try another usb port

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 2, 2011
            <div>

I'm runnin LinuxMint LXDE 11.0, but the above pointed me in the right direction.
thx

            </div>
        </div>
    </li>
</ol>
