# Ubuntu mount a VirtualBox folder on startup

Mount a shared VirtualBox folder on startup in Ubuntu.

```
sudo vim /etc/rc.local
```

```
sharename="MySharedFolder"
sudo mount -t vboxsf -o uid=1000,gid=1000 $sharename /mnt/$sharename
```

Type `mount` to view the mount at `/mnt/MySharedFolder`.

Hint: don't use rc.local for gui applications on startup

---

Posted Dec 20, 2015.

https://www.darklaunch.com/2015/12/20/ubuntu-mount-a-virtualbox-folder-on-startup.html