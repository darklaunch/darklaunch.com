<p>Revert a file to a specific version, by using the `git checkout' command.</p>

<code name="bash">
$ git checkout <commit> -- path/to/file.txt
</code>

<p>For example, revert an icon to a previous state.</p>

<code name="bash">
$ git checkout 807eff29 -- static/images/icons/world.svg
</code>