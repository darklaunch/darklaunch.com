Rhythmbox with debugging turned on displayed this when attempting to "Move to Trash":
```
rhythmbox --debug
...
[0x1072040] [rhythmdb_entry_move_to_trash] rhythmdb.c:3848: trashing file:///mnt/path/to/file.mp3 failed: Unable to find or create trash directory
...
```
Reason: the mount had the incorrect (default) uid and gid.
This will show the current uid and guid for the files:
```
ls -n /mnt/path/to/
```

How To Fix: remount the drive and explicitly set the uid and gid:
```
sudo mount -v -t cifs //10.20.1.20/Volume_1 /mnt/server --verbose -o user=myusername,pass=mypassword,uid=1000,gid=1000
```

Now run
```
ls -n /mnt/path/to/
```
and the uid and gid will be 1000 and 1000 and moving files to the trash in Rhythmbox will work.

NOTE: run "id"
```
>>>
id
<<<
uid=1000(user) gid=1000(user)...
```
to print user and group information.

NOTE: more information about mounting using mount and cifs:
```
man mount
```
AND
```
man 8 mount.cifs
```

---

Posted Feb 4, 2010.

https://www.darklaunch.com/2010/02/04/rhythmbox-unable-to-find-or-create-trash-directory-fixed.html

---

3 comments

<ol>
    <li>
        <div>
            anonymous &ndash; May 31, 2011
            <div>
                <p>thanx..that was very useful</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jul 29, 2012
            <div>
                <p>sorry- first time ubuntu user and non techie- where do i go to put in this code? does remount drive mean reinstalling rhythm box?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 6, 2017
            <div>
                <p>but the disk i mount is exact a fat or extfat. no security user id sets. still the problem present there. how do i do with ?</p>
            </div>
        </div>
    </li>
</ol>
