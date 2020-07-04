<p>JavaScript iframe killer</p>

<code name="javascript">
// iframe killer
while ((el=document.getElementsByTagName('iframe')).length) {
    el[0].parentNode.removeChild(el[0]);
}
</code>