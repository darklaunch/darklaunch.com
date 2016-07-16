<p>Using PHP it is possible to get the given variable name as a string -- similar to using the function get_defined_vars() for a traceback.</p>

<p>A possible use case is a situation like a traceback where you call a function with a parameter and you need to know which variable was passed to the original function.</p>

<code name="php">
<?php
function var_name(&$var) {
   foreach ($GLOBALS as $k => $v) {
       $global_vars[$k] = $v;
   }

   // save the variable's original value
   $saved_var = $var;

   // modify the variable whose name we want to find
   $var = !$var;

   // compare the defined variables before and after the modification
   $diff = array_keys(array_diff_assoc($global_vars, $GLOBALS));

   // restore the variable's original value
   $var = $saved_var;

   // return the name of the modified variable
   return $diff[0];
}
</code>

<code name="php">
header('Content-Type: text/plain');

$some_var_name = 'some value foo';
$another_var_name = 'bar';
$yet_another_var = 'baz';

echo '$' . var_name($some_var_name) . ' = ' . $some_var_name . "\n";
echo '$' . var_name($another_var_name) . ' = ' . $another_var_name . "\n";
echo '$' . var_name($yet_another_var) . ' = ' . $yet_another_var . "\n";
</code>

<p>The above code will produce the following output:</p>

<code>
$some_var_name = some value foo
$another_var_name = bar
$yet_another_var = baz
</code>

<p>