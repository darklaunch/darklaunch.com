# Ubuntu clean up / cruft removal

Remove unwanted applications in Ubuntu.

```bash
sudo apt-get --yes remove --purge ubuntuone*
sudo apt-get --yes remove brasero*
sudo apt-get --yes remove gwibber*
sudo apt-get --yes remove libreoffice*
sudo apt-get --yes remove rhythmbox*
sudo apt-get --yes remove thunderbird*
sudo apt-get --yes remove transmission*
sudo apt-get --yes remove unity-lens-shopping
sudo apt-get --yes remove whoopsie # Remove the "Ubuntu Error Reporting" daemon

# For desktop:
install ubuntu tweak
sudo add-apt-repository ppa:tualatrix/ppa
sudo apt-get update
sudo apt-get install ubuntu-tweak
# then Janitor > check all items and click the Clean button

# Finally
sudo apt-get autoremove
```

---

Posted Jan 15, 2014.

https://www.darklaunch.com/2014/01/15/ubuntu-clean-up-cruft-removal.html

---

1 comment

<ol><li><div>

anonymous &ndash; May 28, 2014<div>

lol

</div></div></li></ol>