> Update: This is outdated, please use prepared statements / PHP Data Objects (PDO).

http://code.google.com/p/class-query/

Class Query makes it easy to run a query.
Simply chain the query parameters with ->run(); as the last parameter.

```php
// Basic select
$q = new Query;
$q
	->select()
	->from('`user`')
	->run();

// -> SELECT * FROM `user`
```

```php
// Select using page
$q = new Query;
$q
	->select()
	->from('`user`')
	->limit(20)
	->page(3)
	->run();

// -> SELECT * FROM `user` LIMIT 60,20
```
Query using more advanced parameters:
```php
require 'class-query.php';

$user_id = 123456;
$q = new Query;
$q
	->select(
		array(
			'`user`.`user_id`',
			'`user`.`name`',
			'`user`.`email`'
		)
	)
	->from('`user`')
	->where_equal_to(
		array(
			'`user_id`'=>$user_id
		)
	)
	->limit(1)
	->run();
if ($q) {
	$user = $q->get_selected();
	echo
		'Hello '.$user['name'].',<br />'.
		'Your email is currently set to '.$user['name'].' '.
		'and your user id is '.$user['user_id'].'.<br />'.
		'';
} else {
	echo 'Sorry, user '.$user_id.' not found.';
}
```

Class Query
http://code.google.com/p/class-query/

---


Posted Apr 1, 2009.
https://www.darklaunch.com/2009/04/01/php-sql-query-class.html