The most compatible way to add a favicon is to use a self-closing link element with the rel property containing the words "shortcut" and "icon".

```html
<link rel="shortcut icon" href="path/to/favicon.ico" />
```

The word "shortcut" is a workaround for Internet Explorer if you have an icon that is not named "favicon.ico" or to share the favicon for subdomains.

Lastly, you can omit specifying the favicon at the top of the page as long as your icon is named "favicon.ico" and is available at the root direction; e. g.: http://www.example.com/favicon.ico ...but using this method is not recommended as the page will load before the icon is displayed.

---


Posted Jun 8, 2011.
https://www.darklaunch.com/2011/06/08/favicon-the-most-correct-compatible-way-to-add-a-favorite-shortcut-icon.html