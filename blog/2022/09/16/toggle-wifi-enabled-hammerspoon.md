# Toggle Wifi Enabled - Hammerspoon

Toggle the wifi on and off with a keyboard shortcut using Hammerspoon:

```lua
function toggleWifiEnabled()
    return function()
        print('toggleWifiEnabled')
        if hs.network.interfaceDetails() == nil then
            print('network is off')
            hs.wifi.setPower(true)
            print('network turned on')
        else
            print('network is on')
            hs.wifi.setPower(false)
            print('network turned off')
        end
    end
end
hs.hotkey.bind({'option'}, 'w', toggleWifiEnabled())
```

---

Posted Sep 16, 2022.

https://www.darklaunch.com/2022/09/16/toggle-wifi-enabled-hammerspoon.html