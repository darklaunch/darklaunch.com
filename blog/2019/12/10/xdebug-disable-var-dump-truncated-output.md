<p>Disable truncated html output when using var_dump by configuring xdebug using ini_set:</p>

<code name="php">
ini_set('xdebug.var_display_max_depth', '-1');
ini_set('xdebug.var_display_max_children', '-1');
ini_set('xdebug.var_display_max_data', '-1');
</code>