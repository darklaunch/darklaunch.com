# How refresh is different from clicking "Go"; Refresh; F5; Ctrl+F5; Ctrl+R

```
cached refresh:
	form:
		input retains value
		textarea retains value
		select retains selected
	img:
		revalidate request sent (slower)
		
go:
	form:
		input value reset
		textarea value reset
		select selected reset
	img:
		HTTP_IF_MODIFIED_SINCE (faster)

no cache refresh:
	form:
		input value reset
		textarea value reset
		select selected reset
```

---

Posted Feb 25, 2009.

https://www.darklaunch.com/2009/02/25/how-refresh-is-different-from-clicking-go-refresh-f5-ctrl-f5-ctrl-r.html