```javascript
function dump(arr, level) {
    // dump() from openjs.com
    var dumped_text = "";
    if (!level) level = 0;
    var level_padding = "";
    for (var j = 0; j < level + 1; j++) level_padding += "    ";
    if (typeof(arr) == 'object') {
        for (var item in arr) {
            var value = arr[item];
            if (typeof(value) == 'object') {
                dumped_text += level_padding + "'" + item + "' ...\n";
                dumped_text += dump(value, level + 1);
            } else {
                dumped_text += level_padding + "'" + item + "' => \"" + value + "\"\n";
            }
        }
    } else {
        dumped_text = "===>" + arr + "<===(" + typeof(arr) + ")";
    }
    return dumped_text;
}

function dbg(msg, level) {
    msg = typeof(msg) === 'object' ? dump(msg, level) : msg;
    var $debugbox = $('#dbg');
    if (!($debugbox.length >= 1)) {
        $debugbox = $('<div id="dbg"></div>')
            .css({
                'bottom' : '0',
                'font-family' : 'monospace',
                'font-size' : '90%',
                'position' : 'absolute',
                'width' : '50%'
            });
        $debugbox.append(
            $('<div>').css({
                'border' : '3px solid black',
                'margin' : '10px 0',
                'max-height' : '200px',
                'overflow-y' : 'auto',
                'padding' : '8px'
            }));
        $("body").append($debugbox);
    }

    $debugbox
        .find("> div")
            .append($('<div>').append((new Date).getTime() + ' ' + msg));

    $debugbox
        .find("> div")
            .scrollTop($debugbox.find('> div').prop('scrollHeight'));
}
```

---

Posted Feb 5, 2009.

https://www.darklaunch.com/2009/02/05/awesome-javascript-debugger.html