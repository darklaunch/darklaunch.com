<p>Fix "bind: address already in use" error by finding the process in use and stopping it.</p>

<p>Example error message:</p>

<code name="bash">
$ my_command
2019/04/24 17:09:14 listen tcp 127.0.0.1:3306: bind: address already in use
</code>

<p>Stop the process using port 3306:</p>

<code name="bash">
$ sudo kill $(sudo lsof -t -i:3306)
</code>

<p>Alternate method:</p>

<p>Clear the port, by finding the process using the port.</p>

<p>For example, find a process using port 8000.</p>

<code name="bash">
$ netstat -tulpn | grep 8000
</code>

<p>Running the netstat command will show an id on the far right. Stop the process by passing this process id to the kill command.</p>

<p>For example, if the id was 3746, run the following command.</p>

<code name="bash">
$ kill 3746
</code>