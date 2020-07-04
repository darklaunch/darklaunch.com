<p>Determine if an element is effectively hidden in JavaScript.</p>

<code name="javascript">
function isHidden(e) {
    const style = window.getComputedStyle(e);
    if (
        style.display === 'none' ||
        style.opacity === '0' ||
        style.fontSize === '0px' ||
        style.visibility === 'hidden'
    ) {
        return true;
    }
    return false;
}
</code>

from https://github.com/tiratatp/facebook_adblock/blob/master/src/main.js