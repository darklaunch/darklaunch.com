# Get Angular version of web page using JavaScript

Use this snippet of JavaScript to determine the exact version of Angular a web page is using.

```javascript
> window.getAllAngularRootElements()[0].getAttribute('ng-version')
"9.1.12"
```

Compare with releases listed on project's releases page:
https://github.com/angular/angular/releases

<img alt="" src="/img/uploads/2021-01/javascript-get-angular-version.png" />

---

Posted Jan 16, 2021.

https://www.darklaunch.com/2021/01/16/get-angular-version-of-web-page-using-javascript.html