Use querySelectorAll with forEach to check checkboxes.
```javascript
document.querySelectorAll('[type=checkbox]').forEach((checkbox) => {
  checkbox.checked = true;
});
```