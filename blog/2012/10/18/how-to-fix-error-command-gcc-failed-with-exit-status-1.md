# How to Fix error: command 'gcc' failed with exit status 1

If you get this error like I did when installing a python virtual environment, do the following on the command line:

```bash
sudo apt-get install python2.7-dev
```

And continue to install the virtual environment:

```bash
# install python dev
sudo apt-get install python2.7-dev

# install easy_install
wget http://python-distribute.org/distribute_setup.py
sudo python distribute_setup.py

# pip install virtualenv
sudo easy_install pip
sudo pip install virtualenv
sudo pip install virtualenvwrapper
```

---

Posted Oct 18, 2012.

https://www.darklaunch.com/2012/10/18/how-to-fix-error-command-gcc-failed-with-exit-status-1.html

---

2 comments

<ol><li><div>

anonymous &ndash; May 15, 2013<div>

Hi! I have this problem but on mac! Can you help me?

</div></div><ol><li><div>

anonymous &ndash; May 15, 2013<div>

Look closely at the error log, what do you see causing the command 'gcc' failed with exit status 1 error?

</div></div></li></ol></li></ol>