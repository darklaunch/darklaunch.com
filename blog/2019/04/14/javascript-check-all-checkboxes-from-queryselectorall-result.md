# JavaScript check all checkboxes from querySelectorAll result

Use querySelectorAll with forEach to check checkboxes.

```javascript
document.querySelectorAll('[type=checkbox]').forEach((checkbox) => {
  checkbox.checked = true;
});
```

---

Posted Apr 14, 2019.

https://www.darklaunch.com/2019/04/14/javascript-check-all-checkboxes-from-queryselectorall-result.html