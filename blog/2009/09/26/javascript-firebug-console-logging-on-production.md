This JavaScript snippet adds console.* functions to the page. Functions like console.log() will not fail even without debugging support. For example, some older versions of Internet Explorer will throw an error if you use a console.log(). Add this script to the top of you script and you will not need to remove any `console` functions.

```javascript
(function() {
    try {
        console.log('');
    }
    catch (e) {
        window.console = {};

        var names = [
            'log',
            'debug',
            'info',
            'warn',
            'error',
            'assert',
            'clear',
            'dir',
            'dirxml',
            'trace',
            'group',
            'groupCollapsed',
            'groupEnd',
            'time',
            'timeEnd',
            'timeStamp',
            'profile',
            'profileEnd',
            'count',
            'exception',
            'table',
        ];

        for (var i = 0; i < names.length; ++i) {
            window.console[names[i]] = function() {};
        }
    }
})();
```

The available console functions for Firebug:

```javascript
console.log(object[, object, ...])
console.debug(object[, object, ...])
console.info(object[, object, ...])
console.warn(object[, object, ...])
console.error(object[, object, ...])
console.assert(expression[, object, ...])
console.clear()
console.dir(object)
console.dirxml(node)
console.trace()
console.group(object[, object, ...])
console.groupCollapsed(object[, object, ...])
console.groupEnd()
console.time(name)
console.timeEnd(name)
console.timeStamp(name)
console.profile([title])
console.profileEnd()
console.count([title])
console.exception(error-object[, object, ...])
console.table(data[, columns])
```

### More about Firebug, the Command Line and the Console API
http://getfirebug.com/commandline
http://getfirebug.com/wiki/index.php/Console_API

---

Posted Sep 26, 2009.

https://www.darklaunch.com/2009/09/26/javascript-firebug-console-logging-on-production.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Dec 11, 2013
            <div>
```javascript
(function (win) {
&nbsp;&nbsp;&nbsp;&nbsp;var method;
&nbsp;&nbsp;&nbsp;&nbsp;var dummy = function() {};
&nbsp;&nbsp;&nbsp;&nbsp;var methods = ('assert,count,debug,dir,dirxml,error,exception,group,' +
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'groupCollapsed,groupEnd,info,log,markTimeline,profile,profileEnd,' +
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'time,timeEnd,trace,warn').split(',');
&nbsp;&nbsp;&nbsp;&nbsp;while (method = methods.pop()) {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; win[method] =  win[method] || dummy;
&nbsp;&nbsp;&nbsp;&nbsp;}
})(window.console = window.console || {});
```
            </div>
        </div>
    </li>
</ol>
