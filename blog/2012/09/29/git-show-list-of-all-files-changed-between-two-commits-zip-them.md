<p>To show a list of the files changed between git commits, do the following:</p>

<code>
$ git diff --name-only SHA1 SHA2
</code>

<p>To also, zip the resulting files, pipe the response to `xargs' and `zip' as such:</p>

<code>
$ git diff --name-only SHA1 SHA2 | xargs zip /path/to/file.zip
</code>

<img alt="" src="/img/uploads/2012-09/git-diff-files-changed.png" />