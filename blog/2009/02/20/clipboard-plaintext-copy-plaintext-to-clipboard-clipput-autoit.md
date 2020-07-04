<p>AutoIt: Put plaintext in clipboard using Ctrl + Shift + C.</p>

<code name="autoit">
#include <GuiConstantsEx.au3>

; AutoIt Code: http://www.autoitscript.com/
$gui = GUICreate('', 500, 300, 0, 0)

; input that will receive richtext clipboard data
$input_clipboard = GuiCtrlCreateInput('my hidden input', 0, 0, 0, 0)

; copy plaintext to clipboard: ctrl+shift+c (normal copy to clipboard ctrl+c)
HotKeySet('^+c', 'ClipPutPlainText') ; ctrl+shift+c

; replaces richtext in clipboard with plaintext
Func ClipPutPlainText()
	; set input value to whatever is currently in clipboard
	GUICtrlSetData($input_clipboard, ClipGet())
	; put plaintext data in clipboard
	ClipPut(GUICtrlRead($input_clipboard))
EndFunc

While 1
	$msg = GUIGetMsg()
	Switch $msg
		Case $GUI_EVENT_CLOSE
			Exit
	EndSwitch
WEnd
</code>

This script basically does the same thing as pasting your clipboard into notepad and then copying it back into the clipboard.

More useful hotkeys:
http://authoitkey.googlecode.com/