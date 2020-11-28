UPDATE:
> Use Google Chrome and Chromium "Preferences" file to permananently disable referrer headers. http://darklaunch.com/2011/08/24/disable-a-referring-url-in-chrome-and-chromium

UPDATE 2:
> Use Referer Control: https://chrome.google.com/webstore/detail/referer-control/hnkcfpcejkafcihlgbojoidoihckciin

---

Google Chrome and Chromium send referring headers when you click on a link, submit a form, etc. To disable this "feature", run Chrome or Chromium with the "no-referrers" option.

```
chromium-browser --no-referrers
```

### Allowing Referer Headers
Using the default settings of including referring information may present a privacy/security risk. Requests to web pages may include this information as part of the HTTP Protocol and it tells what page you came from -- this additional information may also be used to track you.

### Available Chromium Switches
The full list of available chromium switches is listed here under: "Don't send HTTP-Referer headers"
http://src.chromium.org/svn/trunk/src/content/common/content_switches.cc

### Firefox send referer header setting
In Firefox, the option is available in about:config under "network.http.sendRefererHeader" and you want to set this to 0.

* 0 - Never send the Referer header or set document.referrer.
* 1 - Send the Referer header when clicking on a link, and set document.referrer for the following page.
* 2 - Send the Referer header when clicking on a link or loading an image, and set document.referrer for the following page. (Default)

### JavaScript document.referrer field
The referring url is available from the document.referrer field.

---

Posted May 7, 2011.

https://www.darklaunch.com/2011/05/07/chrome-disable-referer-headers.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Aug 9, 2012
            <div>
                <p>Note content_switches.cc moved to <a href="http://src.chromium.org/svn/trunk/src/content/public/common/content_switches.cc">http://src.chromium.org/svn/trunk/src/content/public/common/content_switches.cc</a></p>
            </div>
        </div>
    </li>
</ol>
