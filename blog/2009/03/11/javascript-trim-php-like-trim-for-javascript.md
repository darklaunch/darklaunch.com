Trim JavaScript string function.

Similar to PHP's trim().

```javascript
/**
 * String Trim
 * 
 * str.trim();
 * str.ltrim();
 * str.rtrim();
 * 
 * trim(str);
 * ltrim(str);
 * rtrim(str);
 * 
 */

String.prototype.trim = function() {
	return this.replace(/^\s+|\s+$/g, "");
};

String.prototype.ltrim = function() {
	return this.replace(/^\s+/, "");
};

String.prototype.rtrim = function() {
	return this.replace(/\s+$/, "");
};

function trim(str, chars) {
	return ltrim(rtrim(str, chars), chars);
}

function ltrim(str, chars) {
	chars = chars || "\\s";
	return str.replace(new RegExp("^[" + chars + "]+", "g"), "");
}

function rtrim(str, chars){
	chars = chars || "\\s";
	return str.replace(new RegExp("[" + chars + "]+$", "g"), "");
}
```