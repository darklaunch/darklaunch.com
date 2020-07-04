To merge kwargs options, use the dictionary update method.
```python
def fetch_page(**kwargs):
    options = {
        'method': 'GET',
        'url': 'https://www.example.com/',
        'follow_redirects': False,
        'data': {},
    }
    options.update(kwargs)
    print('options are now: %s' % options)


fetch_page()
# {'url': 'https://www.example.com/', 'follow_redirects': False, 'data': {}, 'method': 'GET'}

fetch_page(url='https://www.google.com/search?q=hello')
# {'url': 'https://www.google.com/search?q=hello', 'follow_redirects': False, 'data': {}, 'method': 'GET'}

fetch_page(url='https://www.example.com/login', method='POST', data={
    'username': 'myusername',
    'password': 'mypassword'
})
# {'url': 'https://www.example.com/login', 'follow_redirects': False, 'data': {'username': 'myusername', 'password': 'mypassword'}, 'method': 'POST'}
```