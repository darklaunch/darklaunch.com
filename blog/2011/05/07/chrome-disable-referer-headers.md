UPDATE:
<blockquote>
Use Google Chrome and Chromium "Preferences" file to permananently disable referrer headers. http://darklaunch.com/2011/08/24/disable-a-referring-url-in-chrome-and-chromium
</blockquote>

UPDATE 2:
<blockquote>
Use Referer Control: https://chrome.google.com/webstore/detail/referer-control/hnkcfpcejkafcihlgbojoidoihckciin
</blockquote>

---<hr />

Google Chrome and Chromium send referring headers when you click on a link, submit a form, etc. To disable this "feature", run Chrome or Chromium with the "no-referrers" option.

```
chromium-browser --no-referrers
```

<h3>Allowing Referer Headers</h3>
Using the default settings of including referring information may present a privacy/security risk. Requests to web pages may include this information as part of the HTTP Protocol and it tells what page you came from -- this additional information may also be used to track you.

<h3>Available Chromium Switches</h3>
The full list of available chromium switches is listed here under: "Don't send HTTP-Referer headers"
http://src.chromium.org/svn/trunk/src/content/common/content_switches.cc


<h3>Firefox send referer header setting</h3>
In Firefox, the option is available in about:config under "network.http.sendRefererHeader" and you want to set this to 0.

<ol>
    <li>0 - Never send the Referer header or set document.referrer.</li>
    <li>1 - Send the Referer header when clicking on a link, and set document.referrer for the following page.</li>
    <li>2 - Send the Referer header when clicking on a link or loading an image, and set document.referrer for the following page. (Default)</li>
</ol>

<h3>JavaScript document.referrer field</h3>
The referring url is available from the document.referrer field.