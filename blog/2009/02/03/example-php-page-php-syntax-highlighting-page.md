```php
<?php
/**
 * Define MyClass
 */
class MyClass{
    // Declare a public constructor
    public function __construct() { }

    // Declare a public method
    public function MyPublic() { }

    // Declare a protected method
    protected function MyProtected() { }

    // Declare a private method
    private function MyPrivate() { }

    // This is public
    function Foo(){
        $this->MyPublic();
        $this->MyProtected();
        $this->MyPrivate();
    }
}

$myclass = new MyClass;
$myclass->MyPublic(); // Works
$myclass->MyProtected(); // Fatal Error
$myclass->MyPrivate(); // Fatal Error
$myclass->Foo(); // Public, Protected and Private work

// Valid constant names
define("TITLE", "Example");
define("TITLE", "Exa $this_is_a_variable mple");

// Page header
include 'header.inc';

echo
    '<div>' .
        '<form action="/">' .
            '<div>' .
                '<label for="q">' .
                    'Search the internets' .
                    (!empty($_COOKIE['name']) ?
                        ' ' . htmlspecialchars($_COOKIE['name']) : ''
                    ) .
                    '<input id="q" name="q" type="text" value="" />' .
                '</label>' .
                '<input type="submit" value="Go" />' .
            '</div>' .
        '</form>' .
    '</div>' .
    '';

// JavaScript
include 'javascript.inc';

/**
 * Lazy load function to prevent regex from being stuffed in
 * cache.
 */
protected function _loadRegex() {
    $oct = '(?:25[0-5]|2[0-4][0-9]|1[0-9]{2}|[1-9][0-9]|[0-9])'; // 0-255
    $this->ip4 = "(?:{$oct}\\.{$oct}\\.{$oct}\\.{$oct})"; // PHP complex variable
}
```

---


Posted Feb 3, 2009.
https://www.darklaunch.com/2009/02/03/example-php-page-php-syntax-highlighting-page.html