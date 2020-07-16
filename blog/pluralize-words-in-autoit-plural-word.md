```autoit
Func plural($count, $singular, $plural = "s")
    If $plural == "s" Then
        $plural = $singular & $plural
    EndIf
    Return _Iif($count == 1, $singular, $plural)
EndFunc
```