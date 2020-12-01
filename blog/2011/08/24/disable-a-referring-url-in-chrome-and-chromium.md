UPDATE:
> Use Referer Control: https://chrome.google.com/webstore/detail/referer-control/hnkcfpcejkafcihlgbojoidoihckciin

---

To permanently disable a referring url in Google Chrome and Chromium, use the following setting in your "Preferences" file to stop sending a referer header on HTTP requests.

The setting is called "enable_referrers" and it needs to be set to false (no quotes) in the json-encoded Preferences ( ~/.config/chromium/Default/Preferences ) file. For Google Chrome look in ~/.config/google-chrome/Default/Preferences

```javascript
{
   ...
   "enable_referrers": false,
   ...
}
```

```py
import json
import os
import time

# current prefs
pref_path = '{0}/.config/chromium/Default/Preferences'.format(os.getenv('HOME'))
prefs = open(pref_path, 'r+')
json_prefs = prefs.read()

# backup
old_prefs = open('{0}.{1}'.format(pref_path, time.time()), 'w')
old_prefs.write(json_prefs)
old_prefs.close()

# disable referrers
new_prefs = json.loads(json_prefs)
new_prefs['enable_referrers'] = False
new_json_prefs = json.dumps(new_prefs, sort_keys=True, indent=4)

# save
prefs.write(new_json_prefs)
prefs.close()

print('DONE')
```

Notes:
```
# http://src.chromium.org/svn/trunk/src/chrome/common/pref_names.cc
// Whether to enable sending referrers.
const char kEnableReferrers[] = "enable_referrers";
```

Other files containing references to "enable_referrers":
http://src.chromium.org/svn/trunk/src/content/common/view_messages.h
http://src.chromium.org/svn/trunk/src/content/common/renderer_preferences.h
http://src.chromium.org/svn/trunk/src/chrome/browser/net/chrome_network_delegate.cc

---

Posted Aug 24, 2011.

https://www.darklaunch.com/2011/08/24/disable-a-referring-url-in-chrome-and-chromium.html

---

4 comments

<ol><li><div>

anonymous &ndash; Aug 30, 2011<div>

for Google Chrome on Windows look in:
C:\Users\USERNAME\AppData\Local\Google\Chrome\User Data\Default\Preferences

</div></div></li><li><div>

anonymous &ndash; Nov 3, 2011<div>

Google Chrome on OSX is located ~/Library/Application Support/Google/Chrome/Default/Preferences

</div></div></li><li><div>

anonymous &ndash; Nov 4, 2011<div>

<a href="http://src.chromium.org/viewvc/chrome/trunk/src/content/public/common/content_switches.cc">http://src.chromium.org/viewvc/chrome/trunk/src/content/public/common/content_switches.cc</a>

</div></div></li><li><div>

anonymous &ndash; Feb 16, 2012<div>

for Chromium on OSX look in ~/Library/Application Support/Chromium/Default/Preferences

</div></div></li></ol>