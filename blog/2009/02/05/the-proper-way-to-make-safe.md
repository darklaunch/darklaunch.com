<p>The proper way to make untrusted user input safe when printing data, is to use htmlspecialchars().</p>

<code name="php">
<?php
$unsafe_username = $_GET['username'];
echo 'hello ' . htmlspecialchars($unsafe_username, ENT_QUOTES, 'UTF-8');
</code>