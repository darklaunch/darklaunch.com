# Use BlockSite with Firefox 3.5; Ubuntu

1.  Open the file "/home/user/.mozilla/firefox/YOURPROFILE/extensions/{dd3d7613-0246-469d-bc65-2a3cc1668adc}/install.rdf"

2. Edit the file to update the maxVersion to "4.0.*":
```
<em:targetApplication>
	<Description>
		<em:id>{ec8030f7-c20a-464f-9b0e-13a3a9e97384}</em:id>
		<em:minVersion>2.0</em:minVersion>
		<em:maxVersion>4.0.*</em:maxVersion>
	</Description>
</em:targetApplication>
```
The file previously read:
```
<em:maxVersion>3.0.*</em:maxVersion>
```

NOTE: You may need to delete the extension's folder ("/{dd3d7613-0246-469d-bc65-2a3cc1668adc}/"), run Firefox so BlockSite is missing from Add-ons and then close the browser. Lastly, restore the deleted folder from trash so the browser can detect the changes and restart Firefox.

---

Posted Jul 6, 2009.

https://www.darklaunch.com/2009/07/06/use-blocksite-with-firefox-3-5-ubuntu.html