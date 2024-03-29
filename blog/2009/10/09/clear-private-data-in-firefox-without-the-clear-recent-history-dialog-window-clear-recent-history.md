# Clear Private Data In Firefox WITHOUT the "Clear Recent History" Dialog Window; Clear Recent History

<strong>UPDATE</strong>: Sanitisminau will clear your history WITHOUT asking.
https://addons.mozilla.org/en-US/firefox/addon/5364/

<strong>UPDATE 2</strong>: Clear private data with alert notification (and without asking):
1. Save the addon using the link above (right click and "Save Link As").
2. Open addon-5364-latest.xpi in an archive manager (like File Roller).
3. Edit addon-5364-latest.xpi/chrome/sanitisminau.jar/content/sanitisminau.js
4. Replace the code with:
```javascript
var Sanitisminau = {
	onLoad: function() {
		document.getElementById("Tools:Sanitize").setAttribute("oncommand", "Sanitisminau.goansanitismi();");
		document.getElementById("sanitizeItem").setAttribute("hidden", true);
	},
	
	goansanitismi: function() {
		var alertService = Components.classes["@mozilla.org/alerts-service;1"].getService(Components.interfaces.nsIAlertsService);
		var s = new Sanitizer();
		s.range = Sanitizer.getClearRange();
		s.ignoreTimespan = false;
		s.prefDomain = "privacy.cpd.";
		try {
			s.sanitize();
			alertService.showAlertNotification(null, "Success", "Private Data Cleared!", false, "", null);
		}
		catch (er) {
			alertService.showAlertNotification(null, "ERROR", er, false, "", null);
		}
	}
}; 

window.addEventListener("load", function(e) { Sanitisminau.onLoad(e); }, false); 
```
5. Install the addon you updated. Type something like file:///home/user/Downloads/addon-5364-latest.xpi (or wherever you saved the addon) into the Firefox url bar and a software installation confirmation will appear. Click "Install Now" after the count down. Restart Firefox.

---

To clear private data in Firefox without the confirmation window, do the following:

1. Install Keyconfig.
2. Add a new key named Clear Private Data.
3. Add the following code:
```javascript
function evalScript(script, callback){
	try {
		eval.call(window, script);
		callback();
	}
	catch (er){
		alertService.showAlertNotification(null, "ERROR", er, false, "", null);
	}
}

function getScript(scriptName, callback){
	var gXMLHttpRequest;
	gXMLHttpRequest = new XMLHttpRequest();
	gXMLHttpRequest.onload =
		function(e){
			evalScript(gXMLHttpRequest.responseText, callback);
		};
	gXMLHttpRequest.open("GET", "chrome://browser/content/" + scriptName);
	gXMLHttpRequest.send(null);
}

var alertService = Components.classes["@mozilla.org/alerts-service;1"].getService(Components.interfaces.nsIAlertsService);
getScript("sanitize.js",
	function(){
		try{
			var s = new Sanitizer();
			s.prefDomain = "privacy.cpd.";
			s.sanitize();
			alertService.showAlertNotification(null, "Success", "Private Data Cleared!", false, "", null);
		}
		catch(er){
			alertService.showAlertNotification(null, "ERROR", er, false, "", null);
		}
	}
);
```

4. Set your preferred hotkey. Something like Alt+Ctrl+Shift+Del.
5. Open a new window for the new hotkey to work. Press the hotkey you set and a notification in the corner will appear.

---

Posted Oct 9, 2009.

https://www.darklaunch.com/2009/10/09/clear-private-data-in-firefox-without-the-clear-recent-history-dialog-window-clear-recent-history.html

---

2 comments

<ol><li><div>

anonymous &ndash; Feb 6, 2010<div>

no worky for 3.6

</div></div></li><li><div>

anonymous &ndash; Feb 6, 2010<div>

Use the Sanitisminau Firefox extension to clear your history without asking
https://addons.mozilla.org/en-US/firefox/addon/5364/

</div></div></li></ol>