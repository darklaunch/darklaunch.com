<img alt="" src="/img/uploads/2011-11/bash-write-stdout-to-file-using-tee.png" />

<p>To display dual output on standard output (stdout) and write or append the output to a file, use tee. For example, do the following:</p>

<code name="sh">
python ./myscript.py | tee -a output.log
</code>

<p>The output from the script is piped to tee and tee prints to stdout and appends to the specified log file.</p>
