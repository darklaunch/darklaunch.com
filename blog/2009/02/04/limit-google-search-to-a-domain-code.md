# Limit Google Search To A Domain; Code

You can limit a Google search to a specific domain using the following code. Change the value of the hidden input to the site of your choice.

```html
<form action="https://www.google.com/search">
	<div>
		<input name="sitesearch" type="hidden" value="darklaunch.com" />
		<input name="q" type="text" value="" />
		<input type="submit" value="Search" />
	</div>
</form>
```

Form is implied GET without method="get".
The &lt;input name="sitesearch" type="hidden" value="darklaunch.com" /> targets only the specified domain.

---

Posted Feb 4, 2009.

https://www.darklaunch.com/2009/02/04/limit-google-search-to-a-domain-code.html