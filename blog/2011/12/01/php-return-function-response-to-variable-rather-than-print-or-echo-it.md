<p>To capture the function's response or output to a variable, use the following function:</p>

<code name="php">
function get_contents($function) {
    ob_start();
    $function();
    $contents = ob_get_contents();
    ob_end_clean();

    return $contents;
}
</code>

<p>To use, pass an anonymous function to get_contents().</p>

<p>Examples:</p>

<code name="php">
// Example: get function's response to variable.
function add($this, $that) {
    echo $this . ' + ' . $that . ' = ' . ($this + $that);
}

$example = get_contents(function() {
    add(1, 1);
});

echo $example . "\n"; // 1 + 1 = 2
</code>
<code name="php">
// Example 2: get function's response using return. Even if the function echos output, it can be captured to a variable.
// Compare print_r() that has a return parameter to var_dump() that has no such parameter.

$return = true;
$example2 = print_r(array('a', 'b', 'c'), $return);

// Solution: use get_contents() to capture the function's response to a variable.
$example3 = get_contents(function() {
    var_dump(array('a', 'b', 'c'));
});

echo $example3;
// array(3) {
//   [0]=>
//   string(1) "a"
//   [1]=>
//   string(1) "b"
//   [2]=>
//   string(1) "c"
// }
</code>

<p>Note: Anonymous functions are available since PHP 5.3.0.</p>