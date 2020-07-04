<p>Install guest additions in Ubuntu VirtualBox.</p>

<p>Download latest guest additions iso at http://download.virtualbox.org/virtualbox/</p>

<code>
$ wget http://download.virtualbox.org/virtualbox/4.3.8/VBoxGuestAdditions_4.3.8.iso
$ mkdir ~/vbox
$ sudo mount VBoxGuestAdditions_4.3.8.iso ~/vbox
$ sudo bash ~/vbox/VBoxLinuxAdditions.run
$ ls /media/</code>

<p>Your shared folders will now be accessible without restarting.</p>

<p>OR download to the host. Mount the iso on the guest and install.</p>

<code>
$ mkdir ~/vbox
$ sudo mount /dev/sr0 ~/vbox
$ sudo bash ~/vbox/VBoxLinuxAdditions.run</code>