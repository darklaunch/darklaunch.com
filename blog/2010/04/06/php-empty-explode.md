Explode a string with no empty elements. Similar to C# Split String: StringSplitOptions.RemoveEmptyEntries.

<code name="php">
function eexplode($separator, $string) {
	$array = explode($separator, $string);
	foreach ($array as $key => $val) {
		if (empty($val)) {
			unset($array[$key]);
		}
	}
	return $array;
}
</code>

NOTE: preg_split() using the PREG_SPLIT_NO_EMPTY flag is another option.