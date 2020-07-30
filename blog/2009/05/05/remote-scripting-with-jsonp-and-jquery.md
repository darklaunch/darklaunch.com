Using JSONP allows for cross-domain HTTP GET requests. The following code uses jQuery to call the Flickr API for a list of photos returned in JSON.

```html
<div id="photos"></div>
```

```javascript
$.ajax({
	type: 'GET',
	url: 'http://api.flickr.com/services/feeds/photos_public.gne?format=json&jsoncallback=?',
	dataType: 'jsonp',
	success: function(data){
		$.each(data.items, function(i, item){
			$('<img/>').attr('src', item.media.m).appendTo('#photos');
		});
	}
});
```

NOTE: Updating is also possible using a GET request, but limited to around 2000 characters for some browsers and not recommended.

---

Posted May 5, 2009.
https://www.darklaunch.com/2009/05/05/remote-scripting-with-jsonp-and-jquery