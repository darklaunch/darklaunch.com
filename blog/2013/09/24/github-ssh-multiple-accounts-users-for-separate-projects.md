Use multiple accounts for separate github projects.

Create private and public keys. This command will create an RSA key with an empty comment (as it's not required). Run this command and save the id_rsa file using different names for each project.
```
$ ssh-keygen -t rsa -C ""
```

Edit the ssh config to add separate configurations for each project.
```
$ vim ~/.ssh/config
```

Add your first project to the configuration.
```
Host github.com-some-project
HostName github.com
User git
IdentityFile ~/.ssh/some-project_id_rsa
```

Add the second project to the configuration. The "Host" in each ssh configuration group needs to be unique.
```
Host github.com-another-project
HostName github.com
User git
IdentityFile ~/.ssh/another-project_id_rsa
```

Clone the project. Note that we are using a modified clone command that uses the "Host" specified in the configuration ("github.com-some-project"). Also set the user name and email for the project that will be used when committing changes.
```
$ cd ~/Projects
$ git clone git@github.com-some-project:some-project/some-project.git
$ cd ~/Projects/some-project
$ git config user.name "some-project"
$ git config user.email "username+some-project@example.com"
```

Repeat the git clone for the next project. This time changing the "Host" again to the other project's "Host" specified in the configuration.
```
$ cd ~/Projects/
$ git clone git@github.com-another-project:another-project/another-project.git
$ cd ~/Projects/another-project
$ git config user.name "another-project"
$ git config user.email "username+another-project@example.com"
```

---

Posted Sep 24, 2013.

https://www.darklaunch.com/2013/09/24/github-ssh-multiple-accounts-users-for-separate-projects.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Jul 19, 2016
            <div>
The .git/config files should look similar to this:

For project A:
[remote "origin"]
&nbsp;&nbsp;&nbsp;&nbsp;url = git@github.com-some-project:some-project/some-project.git
&nbsp;&nbsp;&nbsp;&nbsp;fetch = +refs/heads/*:refs/remotes/origin/*

For project B:
[remote "origin"]
&nbsp;&nbsp;&nbsp;&nbsp;url = git@github.com-another-project:another-project/another-project.git
&nbsp;&nbsp;&nbsp;&nbsp;fetch = +refs/heads/*:refs/remotes/origin/*
            </div>
        </div>
    </li>
</ol>
