# Terminal For Loop; Move Multiple Files; Ubuntu

To move files using a for loop, do the following:

```bash
cd /path/to/files/directory
for i in *.txt; do mv $i ~/Desktop/destination/$i; done
```

The above code will move files with a txt extension to the destination folder on the desktop.

---

Posted Jun 2, 2009.

https://www.darklaunch.com/2009/06/02/terminal-for-loop-move-multiple-files-ubuntu.html

---

4 comments

<ol><li><div>

anonymous &ndash; Aug 21, 2010<div>

Is there any specific reason you'd use that as opposed to 
`mv *.txt ~/Desktop/destination/`
?

</div></div></li><li><div>

anonymous &ndash; Aug 29, 2010<div>

"Is there any specific reason you'd use that as opposed to mv *.txt ~/Desktop/destination/"

for mv not really, but:

```
cd path/to/scripts/
for i in *.sh; do bash $i; done
```

</div></div></li><li><div>

anonymous &ndash; Sep 20, 2010<div>

Batch transcoding:

#!/bin/bash
vcodec="VIDEO_CODEC" 
acodec="AUDIO_CODEC" 
bitrate="VIDEO_BITRATE" 
arate="AUDIO_BITRATE" 
ext="OUTPUT_EXT" 
mux="MUXER" 
vlc="PATH_TO_VLC" 
fmt="INPUT_EXT" 

for a in *$fmt; do 
$vlc -I dummy -vvv "$a" --sout "#transcode{vcodec=$vcodec,vb=$bitrate,acodec=$acodec,ab=$arate,channels=6}:standard{mux=$mux,dst=\"$a.$ext\",access=file}"vlc://quit 
done

</div></div></li><li><div>

anonymous &ndash; Dec 16, 2012<div>

how to arrange the curly brace and write some data under iy in another para

</div></div></li></ol>