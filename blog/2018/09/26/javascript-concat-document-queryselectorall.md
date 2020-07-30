Merge two lists of elements returned by `document.querySelectorAll()`.

Given the following html, select the div and list items.

```html
<div>A</div>

* B
* C
* D

```

```javascript
var someNode = document.querySelector('div');
var moreNodes = document.querySelectorAll('li');
var combined = [someNode].concat(Array.prototype.slice.call(moreNodes));
console.assert(combined.length === 4);
```

The combined variable now contains [div, li, li, li].

Here is a real-world example where comments of a thread are obtained by specifying a target element.

A list of nested comments with one "current" comment.

```html
<div class="comment">
    comment 1
    <div class="comment">
        comment 2
        <div class="comment">
            comment 3
        </div>
    </div>
    <div class="comment">
        comment 4
    </div>
</div>
<div class="comment current">
    comment 5
    <div class="comment">
        comment 6
    </div>
    <div class="comment">
        comment 7
        <div class="comment">
            comment 8
        </div>
        <div class="comment">
            comment 9
        </div>
    </div>
</div>
<div class="comment">
    comment 10
</div>
```

Obtain the list of comments from the "current" target thread.

```javascript
function getCommentsFromThread(targetNode) {
    var childNodes = targetNode.querySelectorAll('.comment');
    var targetAndChildNodes = [targetNode].concat(Array.prototype.slice.call(childNodes));
    var comments = [];
    targetAndChildNodes.forEach(function(element) {
        comments.push(element.childNodes[0].textContent.trim());
    });
    return comments;
};

var target = document.querySelector('.current');
var threadComments = getCommentsFromThread(target);

var expected = [
    'comment 5',
    'comment 6',
    'comment 7',
    'comment 8',
    'comment 9',
];
console.assert(JSON.stringify(expected) === JSON.stringify(threadComments));
```

---

Posted Sep 26, 2018.
https://www.darklaunch.com/2018/09/26/javascript-concat-document-queryselectorall