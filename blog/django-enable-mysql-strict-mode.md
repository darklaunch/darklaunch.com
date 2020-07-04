Enable MySQL strict mode to fix possible data integrity issues.
```python
DATABASES = {
    'default': {
        'ENGINE': '...',
        'NAME': '...',
        'OPTIONS': {
            # Enable MySQL strict mode. "MySQL's Strict Mode fixes many data
            # integrity problems in MySQL, such as data truncation upon
            # insertion, by escalating warnings into errors."
            'init_command': "SET sql_mode='STRICT_TRANS_TABLES'",
        },
    },
}
```
Support full Unicode in MySQL databases by using utf8mb4 instead of utf8.
```python
DATABASES = {
    'default': {
        'ENGINE': '...',
        'NAME': '...',
        'OPTIONS': {
            # Support full Unicode in MySQL databases by using utf8mb4 instead
            # of utf8. Fixes: OperationalError: (1366, "Incorrect string value:
            # ...").
            'charset': 'utf8mb4',
        },
    },
}
```
Use MySQL's READ COMMITTED isolation level rather than the default of REPEATABLE READ.
```python
DATABASES = {
    'default': {
        'ENGINE': '...',
        'NAME': '...',
        'OPTIONS': {
            # Use MySQL's READ COMMITTED isolation level rather than the default
            # of REPEATABLE READ as recommended: "Django works best with and
            # defaults to read committed rather than MySQL's default, repeatable
            # read. Data loss is possible with repeatable read."
            'isolation_level': 'read committed',
        },
    },
}
```
Optionally, configure all database settings.
```python
for key in list(DATABASES.keys()):
    DATABASES[key]['OPTIONS'] = {
        'charset': 'utf8mb4',
        'init_command': "SET sql_mode='STRICT_TRANS_TABLES'",
        'isolation_level': 'read committed',
    }
```