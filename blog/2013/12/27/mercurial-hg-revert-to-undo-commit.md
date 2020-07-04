To undo a commit in Mercurial, use the strip command.
```
$ hg strip
hg: unknown command 'strip'
'strip' is provided by the following extension:

    mq            manage a stack of patches

use "hg help extensions" for information on enabling extensions
```
Fix by enabling the mq extension. Edit the hgrc in the root directory of the repository. The hgrc file is located .hg/hgrc
```
$ cat .hg/hgrc
[paths]
default=ssh://hg@bitbucket.org/username/myproject

$ cat .hg/hgrc
[paths]
default=ssh://hg@bitbucket.org/username/myproject
[extensions]
hgext.mq =
```
Then remove the commit using `hg strip'.
```
$ hg strip <hash_id>
```
kw: hg undo commit, rollback, backout, strip