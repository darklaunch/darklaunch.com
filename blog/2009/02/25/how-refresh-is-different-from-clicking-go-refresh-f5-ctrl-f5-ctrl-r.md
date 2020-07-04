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