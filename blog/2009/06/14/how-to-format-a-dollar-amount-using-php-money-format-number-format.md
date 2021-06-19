# How to format a dollar amount using PHP; money format; number_format

This will format a number into a dollar amount.

```php
function money_format($amount) {
    return number_format($amount, 2, '.', ',');
}
```

Example:
```php
$amount = 123456;
echo money_format($amount); // 123,456.00
```

---

Posted Jun 14, 2009.

https://www.darklaunch.com/2009/06/14/how-to-format-a-dollar-amount-using-php-money-format-number-format.html

---

1 comment

<ol><li><div>

anonymous &ndash; Jan 22, 2010<div>

thanks my friend

</div></div></li></ol>