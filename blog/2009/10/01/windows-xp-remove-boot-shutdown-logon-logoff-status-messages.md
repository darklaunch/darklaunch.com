To remove the message boxes / windows that appear while Windows is loading do the following:

* Start > Run > gpedit.msc > Click OK
* In the Group Policy window select Local Computer Policy > Computer Configuration > Administrative Templates > System.
* On the right, double-click the "Remove Boot / Shutdown / Logon / Logoff status messages" setting and select Enabled, click Apply and OK.

Restart your computer and the loading message windows / boxes will not appear.

NOTE: You may also want to disable the Welcome screen: Control Panel > User Accounts > Change the way users log on or off > uncheck "Use the Welcome screen" > click Apply Options.

---

Posted Oct 1, 2009.

https://www.darklaunch.com/2009/10/01/windows-xp-remove-boot-shutdown-logon-logoff-status-messages.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Jan 12, 2014
            <div>
                <p>If you don't see "System" template, you need to add it manualy.</p>
            </div>
        </div>
    </li>
</ol>
