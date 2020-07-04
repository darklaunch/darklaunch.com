<p>To see whitespace characters in php, use the following function:</p>

<code name="php">
function raw($str) {
    $str = str_replace(array("\t", "\r\n", "\r", "\n"),
                       array('\t', '\r\n', '\r', '\n'), $str);
}
</code>

<code name="php">
// line endings are replaced with literal characters
$str = str_replace("\t", '\t', $str);
$str = str_replace("\r\n", '\r\n', $str);
$str = str_replace("\n", '\n', $str);
$str = str_replace("\r", '\r', $str);
echo $s;

// combined
$str = str_replace(array("\t", "\r\n", "\r", "\n"),
                   array('\t', '\r\n', '\r', '\n'), $str);
echo $s;
</code>