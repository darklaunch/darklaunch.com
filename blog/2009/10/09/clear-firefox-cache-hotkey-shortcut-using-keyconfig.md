UPDATE: https://addons.mozilla.org/en-US/firefox/addon/5364/

---

To clear Firefox's cache using a simple hotkey, do the following:

1. Install Keyconfig.
2. Add a new key named Clear Cache.
3. Add the following code:

```javascript
var cacheService = Components.classes["@mozilla.org/network/cache-service;1"].getService(Components.interfaces.nsICacheService);
var alertsService = Components.classes["@mozilla.org/alerts-service;1"].getService(Components.interfaces.nsIAlertsService);
try{
	cacheService.evictEntries(Components.interfaces.nsICache.STORE_ON_DISK);
	cacheService.evictEntries(Components.interfaces.nsICache.STORE_IN_MEMORY);
	alertsService.showAlertNotification(null, "Success", "Cache cleared!", false, "", null);
}
catch(exception){
	alertsService.showAlertNotification(null, "Exception", exception, false, "", null);
}
```

4. Set your preferred hotkey.
5. Open a new window for the hotkey to work. Press the hotkey you set and a notification in the corner will appear.

NOTE:
Go to about:cache in Firefox to see cache usage before and after clearing cache.

NOTE:
Other Storage Policy:
STORE_ANYWHERE - cache stored in any device
STORE_IN_MEMORY - cache entry in non-persistent storage (RAM)
STORE_ON_DISK - cache entry in persistent storage (HDD)
STORE_ON_DISK_AS_DISK - cache entry in persistent storage in a specific file

---

Posted Oct 9, 2009.

https://www.darklaunch.com/2009/10/09/clear-firefox-cache-hotkey-shortcut-using-keyconfig.html