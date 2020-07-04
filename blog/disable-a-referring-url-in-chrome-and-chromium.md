UPDATE:
> Use Referer Control: https://chrome.google.com/webstore/detail/referer-control/hnkcfpcejkafcihlgbojoidoihckciin


---

To permanently disable a referring url in Google Chrome and Chromium, use the following setting in your "Preferences" file to stop sending a referer header on HTTP requests.

A handy script is available at http://darklaunch.com/scripts/disable-chromium-referrers.py

```
wget http://darklaunch.com/scripts/disable-chromium-referrers.py
chmod +x disable-chromium-referrers.py
python ./disable-chromium-referrers.py
```

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

print 'DONE'
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
