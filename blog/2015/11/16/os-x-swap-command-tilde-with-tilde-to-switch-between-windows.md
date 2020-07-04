Switch to the next most recently used window of the front app by typing tilde instead of command + tilde. Use the following with Karabiner's private.xml file.
```xml
<?xml version="1.0"?>
<root>
    <item>
        <name>Tilde to Command + Tilde</name>
        <identifier>Tilde to Command + Tilde</identifier>
        <autogen>
            __KeyToKey__
            KeyCode::BACKQUOTE | ModifierFlag::NONE,
            KeyCode::BACKQUOTE, ModifierFlag::COMMAND_L
        </autogen>
    </item>
</root>
```