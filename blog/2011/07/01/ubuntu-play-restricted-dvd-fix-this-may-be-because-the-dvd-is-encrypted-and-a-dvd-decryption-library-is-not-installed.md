To fix the following DVD error: "This may be because the DVD is encrypted and a DVD decryption library is not installed.", you need to install libdvdread4 to play your DVD as it is likely encrypted.

Open the Terminal and on the command line, copy and paste the following commands to run them:

```bash
sudo apt-get install libdvdread4
cd /usr/share/doc/libdvdread4
sudo bash install-css.sh
```

This will allow playback of commercial DVDs that are encrypted with CSS (Content Scrambling System) and your disc should now be able to play as intended.

Also, please use VLC Media Player https://www.videolan.org/

Enjoy your movie.

---

Posted Jul 1, 2011.

https://www.darklaunch.com/2011/07/01/ubuntu-play-restricted-dvd-fix-this-may-be-because-the-dvd-is-encrypted-and-a-dvd-decryption-library-is-not-installed.html

---

12 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Oct 20, 2011
            <div>
                <p>wonderful. thanks!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 2, 2011
            <div>
                <p>Thanks!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 4, 2011
            <div>
                <p>do the following?I have no idea what to do with the code, Please be more specific</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 4, 2011
            <div>
                <p>"sudo bash install-css.sh" runs the script</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 11, 2011
            <div>
                <p>Glory!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 18, 2011
            <div>
                <p>Thank you!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 9, 2011
            <div>
                <p>Define 'do'</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 8, 2012
            <div>
                <p>works </p><p>thks!!</p><p>NIN VIDEO</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 9, 2012
            <div>
                <p>well i run de the 3 code line for library decriptor but my dvd media still not playing. please what can i do. the 3 command was correctly installed</p><p></p><p></p><p></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 23, 2012
            <div>
                <p>where is the 'command line'? I don't get it.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 22, 2013
            <div>
                <p>works a charm thanks</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 4, 2014
            <div>
                <p>i donot know where to find deryption library. tellme how tofind the</p>
            </div>
        </div>
    </li>
</ol>
