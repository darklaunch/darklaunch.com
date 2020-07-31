<img alt="" src="/img/uploads/2013-10/dns-323-network-drive.png" />

To mount your DNS-323 on OS X, do the following on the command line.

```
mkdir --parents /Volumes/dns323
mount -t smbfs -o nodev,nosuid //username:password@192.168.1.20/Volume_1 /Volumes/dns323/
```

To fix the error: "mount: realpath /Volumes/dns323: No such file or directory", create the destination mount directory using mkdir.

```
mkdir --parents /Volumes/dns323
```

---

Posted Oct 28, 2013.

https://www.darklaunch.com/2013/10/28/mount-dns-323-on-os-x.html