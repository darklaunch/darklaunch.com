This will allow you to mount a remote ssh filesystem using sshfs (Secure SHell FileSystem):

```bashecho mypassword | sshfs myuser@ftp.mysite.com:/ ~/mnt/mysite -o workaround=rename -o password_stdin```

Replace mypassword, myuser, ftp.mysite.com and mysite.
Example:
```bashecho 4ghNZGpk182q8SvY0kw021JbRb34THaPDN8wyXY679BQPSit5A | sshfs jsmith@ftp.example.com:/ ~/mnt/example -o workaround=rename -o password_stdin```

NOTE: Make sure the mount folder ~/mnt/example exists or create it:
```bashmkdir -p ~/mnt/example```