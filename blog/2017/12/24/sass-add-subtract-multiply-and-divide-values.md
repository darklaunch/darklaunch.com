Use math in sass stylesheets. Input with a file named style.css.

```css
.selector {
  $width: 200;
  $padding: 10;

  padding: #{$padding}px;
  right: -#{$width}px;
  width: #{$width - (2 * $padding)}px;
}
```

Use sass command to watch for file changes in style.scss and compile into style.css.

```bash
$ sass --sourcemap="none" --style "expanded" --watch "style.scss:style.css"
```

```css
.selector {
  padding: 10px;
  right: -200px;
  width: 180px;
}
```

---


Posted Dec 24, 2017.
https://www.darklaunch.com/2017/12/24/sass-add-subtract-multiply-and-divide-values.html