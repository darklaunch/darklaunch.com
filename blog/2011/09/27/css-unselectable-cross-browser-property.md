The user-select CSS Property determines whether the content of an element is selectable. To loosely disable this ability, use the following cross-browser solution.

```css
.unselectable {
   -moz-user-select: -moz-none;
   -ms-user-select: none;
   -khtml-user-select: none;
   -webkit-touch-callout: none;
   -webkit-user-select: none;
   -o-user-select: none;
   user-select: none;
}
```

```css
/* override unselectable */
.unselectable {
   -moz-user-select: auto !important;
   -ms-user-select: auto !important;
   -khtml-user-select: auto !important;
   -webkit-touch-callout: auto !important;
   -webkit-user-select: auto !important;
   -o-user-select: auto !important;
   user-select: auto !important;
}
```

---

Posted Sep 27, 2011.

https://www.darklaunch.com/2011/09/27/css-unselectable-cross-browser-property.html

---

6 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Nov 12, 2011
            <div>
                <p>Pandora does this! eww</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jul 20, 2012
            <div>
                <p>there should be .selectable in the second part of code. isn't it?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jul 20, 2012
            <div>
                <p>&gt;&gt; there should be .selectable in the second part of code. isn't it?</p><p></p><p>no there shouldn't be. the ".unselectable" in the second part overrides the first part with the !important.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 10, 2012
            <div>
                <p>in ie8?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 5, 2013
            <div>
                <p>for ie, use -ms-user-select</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 30, 2014
            <div>
                <p>"-moz-user-select: none;" instead of "-moz-none" is now available starting with Firefox 21.</p>
            </div>
        </div>
    </li>
</ol>
