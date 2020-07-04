Mount a shared VirtualBox folder on startup in Ubuntu.
```
sudo vim /etc/rc.local
```
```
sharename="MySharedFolder"
sudo mount -t vboxsf -o uid=1000,gid=1000 $sharename /mnt/$sharename
```
Type `mount' to view the mount at /mnt/MySharedFolder.

Hint: don't use rc.local for gui applications on startup