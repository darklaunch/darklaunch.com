# hg list users for branch

To list users for a specific branch in hg/Mercurial, use the following:

```bash
$ hg log --only-branch $(hg branch) --template "{author}\n" | sort | uniq
Alice <alice@example.com>
Bob <bob@example.com>
Carol <carol@example.com>
Chuck <chuck@example.com>
Craig <craig@example.com>
Eve <eve@example.com>
```

Note: Please use git.

---

Posted Jul 2, 2013.

https://www.darklaunch.com/2013/07/02/hg-list-users-for-branch.html