Using PHP it is possible to get the given variable name as a string -- similar to using the function get_defined_vars() for a traceback.

A possible use case is a situation like a traceback where you call a function with a parameter and you need to know which variable was passed to the original function.

```php
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
```

```php
header('Content-Type: text/plain');

$some_var_name = 'some value foo';
$another_var_name = 'bar';
$yet_another_var = 'baz';

echo '$' . var_name($some_var_name) . ' = ' . $some_var_name . "\n";
echo '$' . var_name($another_var_name) . ' = ' . $another_var_name . "\n";
echo '$' . var_name($yet_another_var) . ' = ' . $yet_another_var . "\n";
```

The above code will produce the following output:

```
$some_var_name = some value foo
$another_var_name = bar
$yet_another_var = baz
```

---

Posted Jul 9, 2011.

https://www.darklaunch.com/2011/07/09/php-get-the-name-of-the-given-variable-used.html

---

3 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Feb 15, 2012
            <div>

Thanks for posting your solution. It works for variables with "global" scope. To use var_name() with variables defined within a function you would have to scan the array returned by get_defined_vars() instead of $GLOBALS. 
Would be great to have a class with objects that know their own name. E.g. $a1 = new varNameClass(); with a method: $a1-&gt;getName() returning the string 'a1'.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 19, 2014
            <div>

+1

:)

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 12, 2014
            <div>

This is pretty old but.. get_class($this) will give you a class name

            </div>
        </div>
    </li>
</ol>
