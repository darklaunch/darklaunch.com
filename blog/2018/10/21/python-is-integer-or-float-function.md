<p>Return true when the string is an integer or float.</p>

<code name="python">
def is_int_or_float(s):
    try:
        float(s)
    except (TypeError, ValueError):
        return False
    else:
        return True
</code>

<p>Test return value of is_int_or_float, isdigit, and isdecimal.</p>

<code name="python">
char_list = (
    [None, '', '0', '0.0', '0.1', '0.123456789', '1.0'] +
    [
      chr(number) for number in itertools.chain(
        range(1000),
        range(4969, 4978),
        range(8304, 11000),
      )
    ])

line = '-' * 55
checkmark = '\u2713'
print(line)
print('| char        | is_int_or_float | isdigit | isdecimal |')
print(line)
for char in char_list:
    char_is_int_or_float = is_int_or_float(char)
    try:
        char_isdigit = char.isdigit()
    except AttributeError:
        char_isdigit = False
    try:
        char_isdecimal = char.isdecimal()
    except AttributeError:
        char_isdecimal = False
    if char_is_int_or_float or char_isdigit or char_isdecimal:
        print('| {0:>11} | {1:^15} | {2:^7} | {3:^9} |'.format(
            char,
            checkmark if char_is_int_or_float else '',
            checkmark if char_isdigit else '',
            checkmark if char_isdecimal else '',
        ))
</code>

<code>
-------------------------------------------------------
| char        | is_int_or_float | isdigit | isdecimal |
-------------------------------------------------------
|           0 |        ✓        |    ✓    |     ✓     |
|         0.0 |        ✓        |         |           |
|         0.1 |        ✓        |         |           |
| 0.123456789 |        ✓        |         |           |
|         1.0 |        ✓        |         |           |
|           0 |        ✓        |    ✓    |     ✓     |
|           1 |        ✓        |    ✓    |     ✓     |
|           2 |        ✓        |    ✓    |     ✓     |
|           3 |        ✓        |    ✓    |     ✓     |
|           4 |        ✓        |    ✓    |     ✓     |
|           5 |        ✓        |    ✓    |     ✓     |
|           6 |        ✓        |    ✓    |     ✓     |
|           7 |        ✓        |    ✓    |     ✓     |
|           8 |        ✓        |    ✓    |     ✓     |
|           9 |        ✓        |    ✓    |     ✓     |
|           ² |                 |    ✓    |           |
|           ³ |                 |    ✓    |           |
|           ¹ |                 |    ✓    |           |
|           ፩ |                 |    ✓    |           |
|           ፪ |                 |    ✓    |           |
|           ፫ |                 |    ✓    |           |
|           ፬ |                 |    ✓    |           |
|           ፭ |                 |    ✓    |           |
|           ፮ |                 |    ✓    |           |
|           ፯ |                 |    ✓    |           |
|           ፰ |                 |    ✓    |           |
|           ፱ |                 |    ✓    |           |
|           ⁰ |                 |    ✓    |           |
|           ⁴ |                 |    ✓    |           |
|           ⁵ |                 |    ✓    |           |
|           ⁶ |                 |    ✓    |           |
|           ⁷ |                 |    ✓    |           |
|           ⁸ |                 |    ✓    |           |
|           ⁹ |                 |    ✓    |           |
|           ₀ |                 |    ✓    |           |
|           ₁ |                 |    ✓    |           |
|           ₂ |                 |    ✓    |           |
|           ₃ |                 |    ✓    |           |
|           ₄ |                 |    ✓    |           |
|           ₅ |                 |    ✓    |           |
|           ₆ |                 |    ✓    |           |
|           ₇ |                 |    ✓    |           |
|           ₈ |                 |    ✓    |           |
|           ₉ |                 |    ✓    |           |
|           ① |                 |    ✓    |           |
|           ② |                 |    ✓    |           |
|           ③ |                 |    ✓    |           |
|           ④ |                 |    ✓    |           |
|           ⑤ |                 |    ✓    |           |
|           ⑥ |                 |    ✓    |           |
|           ⑦ |                 |    ✓    |           |
|           ⑧ |                 |    ✓    |           |
|           ⑨ |                 |    ✓    |           |
|           ⑴ |                 |    ✓    |           |
|           ⑵ |                 |    ✓    |           |
|           ⑶ |                 |    ✓    |           |
|           ⑷ |                 |    ✓    |           |
|           ⑸ |                 |    ✓    |           |
|           ⑹ |                 |    ✓    |           |
|           ⑺ |                 |    ✓    |           |
|           ⑻ |                 |    ✓    |           |
|           ⑼ |                 |    ✓    |           |
|           ⒈ |                 |    ✓    |           |
|           ⒉ |                 |    ✓    |           |
|           ⒊ |                 |    ✓    |           |
|           ⒋ |                 |    ✓    |           |
|           ⒌ |                 |    ✓    |           |
|           ⒍ |                 |    ✓    |           |
|           ⒎ |                 |    ✓    |           |
|           ⒏ |                 |    ✓    |           |
|           ⒐ |                 |    ✓    |           |
|           ⓪ |                 |    ✓    |           |
|           ⓵ |                 |    ✓    |           |
|           ⓶ |                 |    ✓    |           |
|           ⓷ |                 |    ✓    |           |
|           ⓸ |                 |    ✓    |           |
|           ⓹ |                 |    ✓    |           |
|           ⓺ |                 |    ✓    |           |
|           ⓻ |                 |    ✓    |           |
|           ⓼ |                 |    ✓    |           |
|           ⓽ |                 |    ✓    |           |
|           ⓿ |                 |    ✓    |           |
|           ❶ |                 |    ✓    |           |
|           ❷ |                 |    ✓    |           |
|           ❸ |                 |    ✓    |           |
|           ❹ |                 |    ✓    |           |
|           ❺ |                 |    ✓    |           |
|           ❻ |                 |    ✓    |           |
|           ❼ |                 |    ✓    |           |
|           ❽ |                 |    ✓    |           |
|           ❾ |                 |    ✓    |           |
|           ➀ |                 |    ✓    |           |
|           ➁ |                 |    ✓    |           |
|           ➂ |                 |    ✓    |           |
|           ➃ |                 |    ✓    |           |
|           ➄ |                 |    ✓    |           |
|           ➅ |                 |    ✓    |           |
|           ➆ |                 |    ✓    |           |
|           ➇ |                 |    ✓    |           |
|           ➈ |                 |    ✓    |           |
|           ➊ |                 |    ✓    |           |
|           ➋ |                 |    ✓    |           |
|           ➌ |                 |    ✓    |           |
|           ➍ |                 |    ✓    |           |
|           ➎ |                 |    ✓    |           |
|           ➏ |                 |    ✓    |           |
|           ➐ |                 |    ✓    |           |
|           ➑ |                 |    ✓    |           |
|           ➒ |                 |    ✓    |           |
-------------------------------------------------------
</code>