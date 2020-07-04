<p>Use an in-memory database when running Django tests.</p>

<code name="python">
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
</code>

kw: sqlite3, :memory:, mode=memory