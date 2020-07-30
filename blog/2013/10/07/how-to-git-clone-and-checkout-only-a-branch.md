To git clone a specific branch without downloading the entire repository, do the following:

```
REPOSITORY=https://github.com/django/django
BRANCH=master
mkdir $BRANCH
cd $BRANCH
git init
git remote add -t $BRANCH -f origin $REPOSITORY
git checkout $BRANCH
```

This will download only the requested branch without fetching the full repository.

```
$ git branch --all
* master
  remotes/origin/master
```

---

Posted Oct 7, 2013.
https://www.darklaunch.com/2013/10/07/how-to-git-clone-and-checkout-only-a-branch