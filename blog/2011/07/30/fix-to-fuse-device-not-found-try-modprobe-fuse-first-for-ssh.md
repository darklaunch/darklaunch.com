To fix the error: "fuse: device not found, try 'modprobe fuse' first", do the following on the command line:

```
modprobe fuse
```

Then retry your sshfs command.

---

Posted Jul 30, 2011.

https://www.darklaunch.com/2011/07/30/fix-to-fuse-device-not-found-try-modprobe-fuse-first-for-ssh.html

---

3 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Apr 13, 2012
            <div>
                <p>FATAL: Module fuse not found.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 13, 2012
            <div>
                <p>@"FATAL: Module fuse not found."</p><p></p><p>install the correct kernel-module-fuse rpm. alternatively, install the libfuse2 and fuse-utils packages.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 3, 2012
            <div>
                <p>worked like a charm! thanks</p>
            </div>
        </div>
    </li>
</ol>
