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