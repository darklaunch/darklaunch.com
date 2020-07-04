To list users for a specific branch in hg/Mercurial, use the following:

```
$ hg log --only-branch $(hg branch) --template "{author}\n" | sort | uniq
Alice <alice@example.com>
Bob <bob@example.com>
Carol <carol@example.com>
Chuck <chuck@example.com>
Craig <craig@example.com>
Eve <eve@example.com>
```

Note: Please use git.