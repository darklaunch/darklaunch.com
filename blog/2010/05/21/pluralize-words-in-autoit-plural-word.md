```autoit
Func plural($count, $singular, $plural = "s")
    If $plural == "s" Then
        $plural = $singular & $plural
    EndIf
    Return _Iif($count == 1, $singular, $plural)
EndFunc
```

---


Posted May 21, 2010.
https://www.darklaunch.com/2010/05/21/pluralize-words-in-autoit-plural-word.html