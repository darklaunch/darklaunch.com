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

<ol>
    <li>
        <div>
            anonymous &ndash; Aug 21, 2010
            <div>
                <p>Is there any specific reason you'd use that as opposed to </p><p>mv *.txt ~/Desktop/destination/ </p><p>?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 29, 2010
            <div>
                <p>"Is there any specific reason you'd use that as opposed to mv *.txt ~/Desktop/destination/"</p><p></p><p>for mv not really, but:</p><p></p><p>cd path/to/scripts/</p><p>for i in *.sh; do bash $i; done</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 20, 2010
            <div>
                <p>Batch transcoding:</p><p></p><p>#!/bin/bash</p><p>vcodec="VIDEO_CODEC" </p><p>acodec="AUDIO_CODEC" </p><p>bitrate="VIDEO_BITRATE" </p><p>arate="AUDIO_BITRATE" </p><p>ext="OUTPUT_EXT" </p><p>mux="MUXER" </p><p>vlc="PATH_TO_VLC" </p><p>fmt="INPUT_EXT" </p><p></p><p>for a in *$fmt; do </p><p>$vlc -I dummy -vvv "$a" --sout "#transcode{vcodec=$vcodec,vb=$bitrate,acodec=$acodec,ab=$arate,channels=6}:standard{mux=$mux,dst=\"$a.$ext\",access=file}"<a>vlc://quit</a> </p><p>done</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 16, 2012
            <div>
                <p>how to arrange the curly brace and write some data under iy in another para</p>
            </div>
        </div>
    </li>
</ol>
