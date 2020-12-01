From the official Mercurial website, here is a quote for yet another reason against using Mercurial

> "... if you attempt to use a branch per bugfix, you may eventually run into performance issues. Mercurial is designed to work well with hundreds of branches. It still works quite well with ten thousand branches, but some commands might show noticeable overhead which you will only see after your workflow already stabilized."

<img alt="" src="/img/uploads/2013-03/branch-names-not-disposable.png" />

http://mercurial.selenic.com/wiki/StandardBranching#Don.27t_treat_branch_names_as_disposable

Please use git.

---

Posted Mar 2, 2013.

https://www.darklaunch.com/2013/03/02/yet-another-reason-to-not-use-mercurial.html

---

1 comment

<ol><li><div>

anonymous &ndash; Oct 2, 2013<div>

The .orig files Mercurial leaves after a merge are really annoying as well.

Luckily you can disable this silly behavior my modifying your `$HOME/.hgrc` with:
```
[defaults]
revert = --no-backup
```

</div></div></li></ol>