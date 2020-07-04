<p>To access a page's local variables from a userscript, use a callback:</p>

<code name="javascript">
// ==UserScript==
// @name  Example Script
// @match https://stackoverflow.com/*
// ==/UserScript==

var callback = function() {
    alert('The page is running jQuery version: ' + $.fn.jquery);
};

window.location = 'javascript:(' + callback.toString() + ')();void(0)';
</code>

<p>In your callback, be sure to only use multiline comments if needed ("/* comment */") as single line comments ("//"), will prevent the callback from executing.</p>

<img alt="" src="/img/uploads/2015-06/userscript-access-loca-page-variables.png" />

<p>kw: jQuery, unsafewindow, greasemonkey, chrome, firefox</p>