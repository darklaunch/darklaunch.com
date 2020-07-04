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