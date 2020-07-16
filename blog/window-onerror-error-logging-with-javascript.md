JavaScript window.onerror logging and error handling.
```javascript
(function() {
    window.onerror = function(errorMsg, url, lineNumber) {
        (new Image).src = '/error/?' + [
            // Error message (string).
            'message=' + encodeURIComponent( errorMsg ),
            // Url where error was raised (string).
            'url=' + encodeURIComponent( url ),
            // Line number where error was raised (number).
            'line=' + encodeURIComponent( lineNumber ),
        ].join('&');

        // Return true to prevent the firing of the default event handler.
        return true;
    }
})();
```
More notes on error event fires can be found on http://www.quirksmode.org/dom/events/error.html