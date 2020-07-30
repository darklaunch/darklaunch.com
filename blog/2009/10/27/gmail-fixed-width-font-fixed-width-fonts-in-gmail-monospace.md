To force messages to use a fixed width font, create or edit your Firefox userContent.css file.
```
/home/YOURUSER/.mozilla/firefox/YOURPROFILE/chrome/userContent.css
```
For Windows:
```
C:\Documents and Settings\YOURUSER\Application Data\Mozilla\Firefox\Profiles\YOURPROFILE\chrome\userContent.css
```

Add the following
```css
@-moz-document domain(google.com) {
	.ii, /* message body */
	.Ak  /* textarea when composing */
	{
		font-family:monospace !important;
		font-size:100% !important;
	}
}
```
Restart Firefox and now messages viewed in Gmail will be displayed with a proportional font properly aligned.

---

Posted Oct 27, 2009.
https://www.darklaunch.com/2009/10/27/gmail-fixed-width-font-fixed-width-fonts-in-gmail-monospace