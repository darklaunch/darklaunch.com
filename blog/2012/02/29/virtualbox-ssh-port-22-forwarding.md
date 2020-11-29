To set up SSH access to a VirtualBox VM, you need to forward the appropriate ports.

Open Virtual Box preferences, select the Network tab, select Adapter 1, and click on the "Port Forwarding" button. Add a new rule. Host IP and Guest IP are optional and should be blank. Set Host Port to 2222 and Guest Port to 22.

Note: These Port Forwarding settings take effect immediately in VirtualBox 4, so no need to restart.

Note: Listening on ports 0-1023 requires root permissions, so use a Host Port 1024 and higher. In this case we are using 2222 ("22" + "22").

Connect to the virtual machine via SSH with:

```
ssh -l myusername -p 2222 localhost
```

Additionally, to transfer files to the virtual machine guest, use the following scp command:

```
scp -P 2222 /path/to/source/file.txt myusername@localhost:/path/to/destination/
```

<img alt="" src="/img/uploads/2012-02/virtual-box-ssh-port-forwarding.png" />

---

Posted Feb 29, 2012.

https://www.darklaunch.com/2012/02/29/virtualbox-ssh-port-22-forwarding.html

---

4 comments

<ol><li><div>

anonymous &ndash; Mar 6, 2012<div>

Make sure the client also has ssh server installed and running:
`sudo apt-get install openssh-server`

</div></div></li><li><div>

anonymous &ndash; Nov 30, 2012<div>

This is a correct solution to ssh from host to virtual box Linux! Thanks man!

</div></div></li><li><div>

anonymous &ndash; Dec 27, 2012<div>

I found this very useful and got it working. Thanks.

</div></div></li><li><div>

anonymous &ndash; Apr 10, 2013<div>

It is working and useful.

</div></div></li></ol>