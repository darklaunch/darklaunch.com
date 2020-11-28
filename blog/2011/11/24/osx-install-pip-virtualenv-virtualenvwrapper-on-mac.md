To install pip, virtual environment (virtualenv, virtualenvwrapper) on OS X, do the following on the command line:

```
sudo easy_install pip
sudo pip install virtualenv
sudo pip install virtualenvwrapper
```

To enable the workon tab-completion feature, append the following to your profile file (located at ~/.profile):

```
source /usr/local/bin/virtualenvwrapper.sh
```

Create a directory to house the virtual environments:

```
mkdir ~/.virtualenvs
```

Create a new virtual environment for your project:

```
cd ~/.virtualenvs
virtualenv --no-site-packages myproject
```

* NOTE: Apple's development tools needs to be installed: Xcode
http://itunes.apple.com/us/app/xcode/id448457090

* The "installer" only downloads the file to Applications -- you still need to install Xcode.

* Running the installer normally may freeze. If so, right click and choose "Show Package Contents" then
look for Xcode.mpkg in
/Applications/Install Xcode.app/Contents/Resources/Xcode.mpkg
and run that instead.

<img alt="" src="/img/uploads/2011-11/osx-install-pip-virtual-environment.png" />

---

Posted Nov 24, 2011.

https://www.darklaunch.com/2011/11/24/osx-install-pip-virtualenv-virtualenvwrapper-on-mac.html

---

7 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Mar 19, 2012
            <div>
                <p>To avoid the most common freeze reason while installing Xcode, kill iTunes Helper before you start.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 2, 2012
            <div>
                <p>install easy_install with:</p><p></p><p>wget <a href="http://python-distribute.org/distribute_setup.py">http://python-distribute.org/distribute_setup.py</a></p><p>sudo python distribute_setup.py</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 27, 2012
            <div>
                <p>Thanks.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 27, 2012
            <div>
                <p>fyi, for <code>mkvirtualenv</code>, --no-site-packages is now the default</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 16, 2013
            <div>
                <p>thanks a lot</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 3, 2013
            <div>
                <p>Great concise approach to virtualenvs, thanks!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jul 31, 2013
            <div>
                <p>It works!</p>
            </div>
        </div>
    </li>
</ol>
