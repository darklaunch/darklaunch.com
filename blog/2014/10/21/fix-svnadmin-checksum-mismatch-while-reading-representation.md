Fix the Subversion/svn error: "svnadmin: Checksum mismatch while reading representation".

Verify the integrity of the repository.

```bash
$ svnadmin verify /path/to/repository/
* Verified revision 0.
* Verified revision 1.
* Verified revision 2.
* Verified revision 3.
...

* Verified revision 84.                                                                                                                       
* Verified revision 85.
* Verified revision 86.
svnadmin: Checksum mismatch while reading representation:
   expected:  45e4fa4e2514c0e6c73196cc393f53b7
     actual:  51c6939ae80c3bd8e12c922651e64ae6
```

The checksum mismatch error here means the next version (87) failed as it wasn't successfully verified. Some data stored in the repository changed or got corrupted. In my case, a rogue script did a find and replace across all system files. This affected the checksum of the file when the repository was being checked out and thus the mismatch error.

To fix this, look for the expected checksum string (45e4fa4e2514c0e6c73196cc393f53b7) in a file in the repository.

```bash
$ cd /path/to/repository/
$ grep -Ri "45e4fa4e2514c0e6c73196cc393f53b7" .
Binary file ./db/revs/0/87 matches
```

Edit file where the checksum was found (db/revs/0/87).

```bash
$ vim /path/to/repository/db/revs/0/87
```

```
Find the line beginning with "text:" that contains the checksum value. Replace what was expected (45e4fa4e2514c0e6c73196cc393f53b7) with what was found (51c6939ae80c3bd8e12c922651e64ae6).

Replace:
text: 87 0 941 1689 45e4fa4e2514c0e6c73196cc393f53b7

With this:
text: 87 0 941 1689 51c6939ae80c3bd8e12c922651e64ae6
```

To verify your changes worked, verify the specific revision where the error occurred by using -r with the svnadmin verify command. Remember that this is the last number displayed as "Verified revision XX" plus 1 more.

Before:

```bash
$ svnadmin verify -r 87 /path/to/repository/
svnadmin: Checksum mismatch while reading representation:
   expected:  45e4fa4e2514c0e6c73196cc393f53b7
     actual:  51c6939ae80c3bd8e12c922651e64ae6
```

After:

```bash
$ svnadmin verify -r 87 /path/to/repository/
* Verified revision 87.
```

Repeat these commands for all the checksum mismatch errors. Now the svn checkout command should work.

Note this method changes affects the integrity of the repository. If you know the exact(!) changes that were made to the file or files in the repository, you can change them back and the checksum will succeed.

---

Posted Oct 21, 2014.

https://www.darklaunch.com/2014/10/21/fix-svnadmin-checksum-mismatch-while-reading-representation.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Nov 28, 2017
            <div>
It works. Finally I even fixed the integrity. It's easy to find the name of file which contains broken data. I've compared (binary diff) original file and actual data in revision and found 1 broken byte. Then fixed it via hex editor and welcome back, integrity! Now svnadmin verify passes all revisions fine.
            </div>
        </div>
    </li>
</ol>
