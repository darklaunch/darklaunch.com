<p>To skip the system prompt for the administrator's password, add the following to your sudoers file:</p>

<code>
# Don't prompt for password when using sudo.
user ALL=(ALL) NOPASSWD: ALL</code>

<p>This will modify the sudoers file to skip the sudo password prompt for the current user.</p>

<p>Or in one step, do this on the command line:</p>

<code>
whoami=$(whoami)
sudo bash -c 'echo -e "# Don'\''t prompt for password when using sudo.\n'$whoami' ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers'</code>