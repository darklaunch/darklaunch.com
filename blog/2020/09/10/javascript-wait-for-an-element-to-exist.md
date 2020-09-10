Wait for an element to exist using a JavaScript promise:

```javascript
function waitForElement(selector) {
    return new Promise(function(resolve, reject) {
        var element = document.querySelector(selector);
        if (element) {
            resolve(element);
            return;
        }

        var observer = new MutationObserver(function(mutations) {
            mutations.forEach(function(mutation) {
                var nodes = Array.from(mutation.addedNodes);
                for (var node of nodes) {
                    if (node.matches && node.matches(selector)) {
                        observer.disconnect();
                        resolve(node);
                        return;
                    }

                    if (node.querySelector) {
                        var element = node.querySelector(selector);
                        if (element) {
                            resolve(element);
                            return;
                        }
                    }
                };
            });
        });

        observer.observe(
            document.documentElement,
            {
                childList: true,
                subtree: true,
            }
        );
    });
}
```

Usage:

```javascript
waitForElement('#username')
.then(function(usernameField) {
    console.log('username field found:', usernameField);
});
```

---

Posted Sep 10, 2020.

https://www.darklaunch.com/2020/09/10/javascript-wait-for-an-element-to-exist.html