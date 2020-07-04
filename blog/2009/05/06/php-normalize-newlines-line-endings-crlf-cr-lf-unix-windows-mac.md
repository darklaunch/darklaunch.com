<code name="php">
define('CR', "\r");          // Carriage Return: Mac
define('LF', "\n");          // Line Feed: Unix
define('CRLF', "\r\n");      // Carriage Return and Line Feed: Windows
define('BR', '&lt;br />' . LF); // HTML Break
</code>
<code name="php">
function normalize($s) {
	// Normalize line endings using Global
	// Convert all line-endings to UNIX format
	$s = str_replace(CRLF, LF, $s);
	$s = str_replace(CR, LF, $s);
	// Don't allow out-of-control blank lines
	$s = preg_replace("/\n{2,}/", LF . LF, $s);
	return $s;
}
</code>
<code name="php">
function normalize($s) {
	// Normalize line endings
	// Convert all line-endings to UNIX format
	$s = str_replace("\r\n", "\n", $s);
	$s = str_replace("\r", "\n", $s);
	// Don't allow out-of-control blank lines
	$s = preg_replace("/\n{2,}/", "\n\n", $s);
	return $s;
}
</code>