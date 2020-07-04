If your regex pattern is too greedy, that is, it finds the largest matching case when you want it to find the smallest matching pattern, use a non-greedy selection.

Replace the greedy quantifier with the corresponding non-greedy version.

> "...change * , + , ? , and {} into *? , +? , ?? , and {}? , respectively"


<div style="padding: 39px 19px 14px;">
<table>
    <thead>
        <tr>
            <th>from</th>
            <th>to</th>
        </tr>
    </thead>
    <tbody>
        <tr><td>*</td><td>*?</td></tr>
        <tr><td>+</td><td>+?</td></tr>
        <tr><td>?</td><td>??</td></tr>
        <tr><td>{}</td><td>{}?</td></tr>
    </tbody>
</table>
</div>

More from the Perl Cookbook
http://docstore.mik.ua/orelly/perl/cookbook/ch06_16.htm