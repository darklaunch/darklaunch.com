To use `ssh-copy-id` in OS X, do the following on the command line.

```sh
$ cd
$ curl https://gist.github.com/darklaunch/5045167/raw --output ssh-copy-id
$ chmod +x ssh-copy-id
$ ./ssh-copy-id -i ~/.ssh/id_rsa.pub username@hostname
```

Also, if haven't created key for a specific email address, do this first:

```sh
$ ssh-keygen -t rsa -C "username@example.com"
```

And wherever you save the key, specify that in the ssh-copy-id command
by replacing "~/.ssh/id_rsa.pub" with the appropriate path

Here's a copy of the script for reference

```sh
#!/bin/sh
 
# Shell script to install your public key on a remote machine
# Takes the remote machine name as an argument.
# Obviously, the remote machine must accept password authentication,
# or one of the other keys in your ssh-agent, for this to work.
#
# http://www.devthought.com/2009/09/19/get-ssh-copy-id-in-mac-os-x/
#
 
ID_FILE="${HOME}/.ssh/id_rsa.pub"
 
if [ "-i" = "$1" ]; then
  shift
  # check if we have 2 parameters left, if so the first is the new ID file
  if [ -n "$2" ]; then
    if expr "$1" : ".*\.pub" > /dev/null ; then
      ID_FILE="$1"
    else
      ID_FILE="$1.pub"
    fi
    shift         # and this should leave $1 as the target name
  fi
else
  if [ x$SSH_AUTH_SOCK != x ] && ssh-add -L >/dev/null 2>&1; then
    GET_ID="$GET_ID ssh-add -L"
  fi
fi
 
if [ -z "`eval $GET_ID`" ] && [ -r "${ID_FILE}" ] ; then
  GET_ID="cat ${ID_FILE}"
fi
 
if [ -z "`eval $GET_ID`" ]; then
  echo "$0: ERROR: No identities found" >&2
  exit 1
fi
 
if [ "$#" -lt 1 ] || [ "$1" = "-h" ] || [ "$1" = "--help" ]; then
  echo "Usage: $0 [-i [identity_file]] [user@]machine" >&2
  exit 1
fi
 
# strip any trailing colon
host=`echo $1 | sed 's/:$//'`
 
{ eval "$GET_ID" ; } | ssh $host "umask 077; test -d ~/.ssh || mkdir ~/.ssh ; cat >> ~/.ssh/authorized_keys" || exit 1
 
cat <<EOF
Now try logging into the machine, with "ssh '$host'", and check in:
 
  ~/.ssh/authorized_keys
 
to make sure we haven't added extra keys that you weren't expecting.
 
EOF
```

---


Posted Feb 21, 2013.
https://www.darklaunch.com/2013/02/21/ssh-copy-id-for-os-x.html