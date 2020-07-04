Run python 2.7 using pipenv:
```python
$ mkdir python2
$ cd python2
$ echo -e '[requires]\npython_version = "2.7"' > Pipfile
$ pipenv run python
Python 2.7.10
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
Run python 3 using pipenv:
```python
$ mkdir python3
$ cd python3
$ echo -e '[requires]\npython_version = "3"' > Pipfile
$ pipenv run python
Python 3.7.3
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
Run python 3.6 using pipenv:
```python
$ mkdir python3.6
$ cd python3.6
$ echo -e '[requires]\npython_version = "3.6"' > Pipfile
$ pipenv run python
Warning: Python 3.6 was not found on your system…
You can specify specific versions of Python with:
  $ pipenv --python path/to/python
$ brew install pyenv
$ pyenv install 3.6.7
$ pipenv --python "${HOME}/.pyenv/versions/3.6.7/bin/python" run python
Python 3.6.7
Type "help", "copyright", "credits" or "license" for more information.
>>>
```