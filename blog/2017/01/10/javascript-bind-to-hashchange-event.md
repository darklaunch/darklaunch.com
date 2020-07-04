<p>Bind a function to the hash change event.</p>

<code name="javascript">
function hashChange() {
    console.info('hash changed!');
}

window.addEventListener('hashchange', hashChange, false);
</code>