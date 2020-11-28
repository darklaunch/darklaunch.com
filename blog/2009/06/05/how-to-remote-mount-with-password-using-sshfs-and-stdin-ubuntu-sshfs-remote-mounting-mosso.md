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

Many thanks, great solution

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 8, 2011
            <div>

BRILLIANT!  Thanks.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 2, 2011
            <div>

I'm running this script and keep getting `"Timeout waiting for prompt"`. Any suggestions:
`echo $DESTINATION_PWD | sshfs -o workaround=rename,password_stdin,sshfs_debug $DESTINATION_USER@$DESTINATION_SERVER:$DESTINATION_SERVER_PATH $MOUNT_PATH`

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 3, 2011
            <div>

regarding the timeout... do it first without the `"echo $DESTINATION_PWD | "`

you may need to allow the connection the first time

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 3, 2011
            <div>

... and without `password_stdin`

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 16, 2011
            <div>

Simple and perfect for webserver backup. Thank you!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 20, 2011
            <div>

Thanks. This worked for me. Any security issues with this?

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 20, 2011
            <div>

@"security issues" the entry will be in your bash history if you type out the command

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 28, 2011
            <div>

Just remember to try the command manually first (or ssh to it) because it will fail waiting for the Y/N question ...

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 6, 2011
            <div>

Why won't this work in 'startup applications'?  works just fine in the terminal.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 6, 2011
            <div>

look into using fstab to add mount to startup.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Mar 6, 2012
            <div>

thanks, you are genius!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Mar 12, 2012
            <div>

THX!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 9, 2012
            <div>

Excellent... Mind blowing I would say.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 22, 2012
            <div>

Finally after a rigorous search, I got the answer!!! Thank You soooo much...

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 12, 2013
            <div>

don't work :(

`"remote host has disconnected"`

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 28, 2013
            <div>

This is why I'm here ;-)  

"Just remember to try the command manually first (or ssh to it) because it will fail waiting for the Y/N question ..."

Oops.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 11, 2014
            <div>

BINGO!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 3, 2014
            <div>

thank you, bro!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 26, 2014
            <div>

Very cool. Thanks.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 24, 2014
            <div>

+1

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 29, 2014
            <div>

THIS IS AWESOME! 
Not the most secure but gets the job done!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 26, 2014
            <div>

You're genius! Thank you very much! Greetings from Italy, fabriziorubino.it

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 3, 2015
            <div>

I get the error `"Timeout waiting for prompt"`. I have previously ssh to the server so it's not the y/n prompt. Trying to do this with Cloud9 to a DigitalOcean server. Any ideas?

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 21, 2015
            <div>

How to stick that into fstab or get it working on startup?

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 21, 2015
            <div>

Here is some info on mounting partitions in Ubuntu

<a href="https://help.ubuntu.com/community/Fstab">https://help.ubuntu.com/community/Fstab</a>

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 22, 2015
            <div>

I know how to mount most of the partitions, but fstab will not take echo command...

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 4, 2016
            <div>

I put this in a bash script and it works without getting the password prompt. But when the same script run from Jenkins I keep on getting the same message: `"Timeout waiting for prompt"`, so the Jenkins job just failed. Wonder if anybody observed this and could offer a solution or workaround? Thanks much.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 7, 2016
            <div>

Hi,
after struggling a couple of hours, I found your solution.
Thanks, man!!!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 2, 2016
            <div>

`"Timeout waiting for prompt"` happens due to host identity verification while connecting for the very first time. Simply add `-o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null`. The first option allows you to connect to unknown hosts without prompt, the second option prevents the host key from getting stored in the first place, so you won't run into problems if it changes. This is not very secure, but neither is piping the clear-text password...

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 28, 2018
            <div>

goood

            </div>
        </div>
    </li>
</ol>
