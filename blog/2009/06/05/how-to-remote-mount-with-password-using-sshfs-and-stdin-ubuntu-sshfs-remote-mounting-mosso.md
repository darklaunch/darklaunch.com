This will allow you to mount a remote ssh filesystem using sshfs (Secure SHell FileSystem):

```bash
echo mypassword | sshfs myuser@ftp.mysite.com:/ ~/mnt/mysite -o workaround=rename -o password_stdin
```

Replace mypassword, myuser, ftp.mysite.com and mysite.
Example:
```bash
echo 4ghNZGpk182q8SvY0kw021JbRb34THaPDN8wyXY679BQPSit5A | sshfs jsmith@ftp.example.com:/ ~/mnt/example -o workaround=rename -o password_stdin
```

NOTE: Make sure the mount folder ~/mnt/example exists or create it:
```bash
mkdir -p ~/mnt/example
```

---

Posted Jun 5, 2009.

https://www.darklaunch.com/2009/06/05/how-to-remote-mount-with-password-using-sshfs-and-stdin-ubuntu-sshfs-remote-mounting-mosso.html

---

31 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Feb 8, 2011
            <div>
                <p>Many thanks, great solution</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 8, 2011
            <div>
                <p>BRILLIANT!  Thanks.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 2, 2011
            <div>
                <p>I'm running this script and keep getting <code>"Timeout waiting for prompt"</code>. Any suggestions:</p><p><code>echo $DESTINATION_PWD | sshfs -o workaround=rename,password_stdin,sshfs_debug $DESTINATION_USER@$DESTINATION_SERVER:$DESTINATION_SERVER_PATH $MOUNT_PATH</code></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 3, 2011
            <div>
                <p>regarding the timeout... do it first without the <code>"echo $DESTINATION_PWD | "</code></p><p></p><p>you may need to allow the connection the first time</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 3, 2011
            <div>
                <p>... and without <code>password_stdin</code></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 16, 2011
            <div>
                <p>Simple and perfect for webserver backup. Thank you!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 20, 2011
            <div>
                <p>Thanks. This worked for me. Any security issues with this?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 20, 2011
            <div>
                <p>@"security issues" the entry will be in your bash history if you type out the command</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 28, 2011
            <div>
                <p>Just remember to try the command manually first (or ssh to it) because it will fail waiting for the Y/N question ...</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 6, 2011
            <div>
                <p>Why won't this work in 'startup applications'?  works just fine in the terminal.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 6, 2011
            <div>
                <p>look into using fstab to add mount to startup.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Mar 6, 2012
            <div>
                <p>thanks, you are genius!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Mar 12, 2012
            <div>
                <p>THX!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 9, 2012
            <div>
                <p>Excellent... Mind blowing I would say.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 22, 2012
            <div>
                <p>Finally after a rigorous search, I got the answer!!! Thank You soooo much...</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 12, 2013
            <div>
                <p>don't work :(</p><p></p><p><code>"remote host has disconnected"</code></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 28, 2013
            <div>
                <p>This is why I'm here ;-)  </p><p></p><p>"Just remember to try the command manually first (or ssh to it) because it will fail waiting for the Y/N question ..."</p><p></p><p>Oops.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 11, 2014
            <div>
                <p>BINGO!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 3, 2014
            <div>
                <p>thank you, bro!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 26, 2014
            <div>
                <p>Very cool. Thanks.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 24, 2014
            <div>
                <p>+1</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 29, 2014
            <div>
                <p>THIS IS AWESOME! </p><p>Not the most secure but gets the job done!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 26, 2014
            <div>
                <p>You're genius! Thank you very much! Greetings from Italy, fabriziorubino.it</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 3, 2015
            <div>
                <p>I get the error <code>"Timeout waiting for prompt"</code>. I have previously ssh to the server so it's not the y/n prompt. Trying to do this with Cloud9 to a DigitalOcean server. Any ideas?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 21, 2015
            <div>
                <p>How to stick that into fstab or get it working on startup?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 21, 2015
            <div>
                <p>Here is some info on mounting partitions in Ubuntu</p><p></p><p><a href="https://help.ubuntu.com/community/Fstab">https://help.ubuntu.com/community/Fstab</a></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 22, 2015
            <div>
                <p>I know how to mount most of the partitions, but fstab will not take echo command...</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 4, 2016
            <div>
                <p>I put this in a bash script and it works without getting the password prompt. But when the same script run from Jenkins I keep on getting the same message: <code>"Timeout waiting for prompt"</code>, so the Jenkins job just failed. Wonder if anybody observed this and could offer a solution or workaround? Thanks much.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 7, 2016
            <div>
                <p>Hi,</p><p>after struggling a couple of hours, I found your solution.</p><p>Thanks, man!!!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 2, 2016
            <div>
                <p><code>"Timeout waiting for prompt"</code> happens due to host identity verification while connecting for the very first time. Simply add <code>-o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null</code>. The first option allows you to connect to unknown hosts without prompt, the second option prevents the host key from getting stored in the first place, so you won't run into problems if it changes. This is not very secure, but neither is piping the clear-text password...</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 28, 2018
            <div>
                <p>goood</p>
            </div>
        </div>
    </li>
</ol>
