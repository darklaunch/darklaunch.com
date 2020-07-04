If you get this error like I did when installing a python virtual environment, do the following on the command line:
```
sudo apt-get install python2.7-dev
```

And continue to install the virtual environment:
```
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