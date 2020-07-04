```autoit
Func implode($glue, $pieces)
	Return _ArrayToString($pieces, $glue)
EndFunc   ;==>implode
```

```autoit
#include <String.au3>
#include <Array.au3>

$array = _StringExplode("foo|bar|baz", "|");
For $i = 0 To UBound($array) - 1
	ConsoleWrite("array[" & $i & "] = " & $array[$i] & @CRLF)
Next
; array[0] = foo
; array[1] = bar
; array[2] = baz

ConsoleWrite(implode(",", $array) & @CRLF)
; foo,bar,baz
```