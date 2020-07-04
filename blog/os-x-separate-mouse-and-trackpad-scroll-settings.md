Use Karabiner (https://github.com/tekezo/Karabiner) to change mouse and trackpad scroll settings. Edit private.xml.
```
<?xml version="1.0"?>
<root>
  <devicevendordef>
    <vendorname>SOMEVENDOR</vendorname>
    <vendorid>0x0001</vendorid>
  </devicevendordef>
  <deviceproductdef>
    <productname>SOMEPRODUCT</productname>
    <productid>0x0002</productid>
  </deviceproductdef>
  <item>
    <name>custom</name>
    <identifier>custom</identifier>
    <device_only>DeviceVendor::SOMEVENDOR, DeviceProduct::SOMEPRODUCT</device_only>
    <autogen>__FlipScrollWheel__ Option::FLIPSCROLLWHEEL_VERTICAL</autogen>
  </item>
</root>
```

Replace vendor id 0x0001 and product id 0x0002 with the values from EventViewer. Save private.xml and click the Reload XML button <img alt="" src="/img/uploads/2015-10/reload-xml-button.png" /> under the Change Key tab <img alt="" src="/img/uploads/2015-10/change-key-tab.png" />.

Open EventViewer.app using
```
$ open /Applications/Karabiner.app/Contents/Applications/EventViewer.app
```

<img alt="" src="/img/uploads/2015-10/os-x-eventviewer.png" />