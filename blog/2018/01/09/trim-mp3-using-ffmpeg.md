# Trim mp3 using ffmpeg

Trim a range starting and ending at a certain time.

```bash
$ ffmpeg -i input.mp3 -ss 00:00:03 -to 00:03:42 -acodec copy output.mp3
```

Use `-ss` for the start time.
Use `-to` for the end time.
Note: The order of the parameters is significant.

From `man ffmpeg-utils`, here an accepted syntax for the time fields:

```
[-][<HH>:]<MM>:<SS>[.<m>...]
```

---

Posted Jan 9, 2018.

https://www.darklaunch.com/2018/01/09/trim-mp3-using-ffmpeg.html