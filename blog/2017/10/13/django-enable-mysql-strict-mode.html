<p>Enable MySQL strict mode to fix possible data integrity issues.</p>

<code name="python">
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
</code>

<p>Support full Unicode in MySQL databases by using utf8mb4 instead of utf8.</p>

<code name="python">
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
</code>

<p>Use MySQL's READ COMMITTED isolation level rather than the default of REPEATABLE READ.</p>

<code name="python">
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
</code>

<p>Optionally, configure all database settings.</p>

<code name="python">
for key in list(DATABASES.keys()):
    DATABASES[key]['OPTIONS'] = {
        'charset': 'utf8mb4',
        'init_command': "SET sql_mode='STRICT_TRANS_TABLES'",
        'isolation_level': 'read committed',
    }
</code>