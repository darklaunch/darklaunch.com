Install guest additions in Ubuntu VirtualBox.

Download latest guest additions iso at http://download.virtualbox.org/virtualbox/

```bash
$ wget http://download.virtualbox.org/virtualbox/4.3.8/VBoxGuestAdditions_4.3.8.iso
$ mkdir ~/vbox
$ sudo mount VBoxGuestAdditions_4.3.8.iso ~/vbox
$ sudo bash ~/vbox/VBoxLinuxAdditions.run
$ ls /media/
```

Your shared folders will now be accessible without restarting.

OR download to the host. Mount the iso on the guest and install.

```bash
$ mkdir ~/vbox
$ sudo mount /dev/sr0 ~/vbox
$ sudo bash ~/vbox/VBoxLinuxAdditions.run
```

---


Posted Jul 19, 2014.
https://www.darklaunch.com/2014/07/19/virtualbox-install-guest-additions-ubuntu.html