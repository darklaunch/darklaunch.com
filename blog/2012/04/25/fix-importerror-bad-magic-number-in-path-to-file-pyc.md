<p>To fix the "ImportError: Bad magic number" error, you will need to remove existing .pyc compiled python files.</p>

<code>
$ find . -name "*.pyc" -delete
</code>

<p>Alternatively, if you'd like to run some other command on the files found, use the following syntax:</p>

<code>
$ find . -name "*.pyc" -exec rm {} \;
</code>