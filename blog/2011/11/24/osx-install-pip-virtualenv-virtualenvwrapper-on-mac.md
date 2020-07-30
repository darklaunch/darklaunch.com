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
https://www.darklaunch.com/2011/11/24/osx-install-pip-virtualenv-virtualenvwrapper-on-mac