Use an in-memory database when running Django tests.
```python
# settings.py
TEST_ENV = len(sys.argv) >= 2 and sys.argv[1] == 'test'

if TEST_ENV:
    # Use an in-memory database for tests.
    # "When using SQLite, the tests will use an in-memory database by default".
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.sqlite3',
            'NAME': 'mydatabase',
        }
    }
```

kw: sqlite3, :memory:, mode=memory