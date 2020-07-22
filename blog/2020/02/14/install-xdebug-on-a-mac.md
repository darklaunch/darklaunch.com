Use pecl instead of brew to install xdebug on a Mac.

Install
```
$ pecl install xdebug
```

Confirm installed:
```
$ php -i | grep xdebug
```

Fixes errors: "Error: No code coverage driver is available" and "Error:  Incorrect whitelist config, no code coverage will be generated."