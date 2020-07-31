Why are spreadsheet cells not equal? Here are some tests.

Test cell A1 and B1:

```sh
=ISNUMBER(A1)
=ISNUMBER(B1)

=LEN(A1)
=LEN(B1)

=ENCODEURL(A1)
=ENCODEURL(B1)

=VALUE(A1)=B1
=A1=VALUE(B1)
=VALUE(A1)=VALUE(B1)
```

---

Posted Apr 12, 2020.

https://www.darklaunch.com/2020/04/12/spreadsheet-equality-tests.html