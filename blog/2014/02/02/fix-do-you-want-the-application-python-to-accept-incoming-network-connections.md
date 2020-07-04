<p>With the OS X firewall enabled, you can remove the "Do you want the application "python" to accept incoming network connections?" message.</p>

<img alt="" src="/img/uploads/2014-02/os-x-accept-incoming-network-connections.png" />

<p>Create a self-signed certificate.</p>

<ol>
<li>Open Keychain Access. Applications > Utilities > Keychain Access.</li>
<li>Keychain Access menu > Certificate Assistant > Create a Certificate...</li>
<li>Enter a Name like "My Certificate".</li>
<li>Select Identity Type: Self Signed Root</li>
<li>Select Certificate Type: Code Signing</li>
<li>Check the Let me override defaults box</li>
<li>Click Continue</li>
<li>Enter a unique Serial Number</li>
<li>Enter 7300 for Validity Period.</li>
<li>Click Continue</li>
<li>Click Continue for the rest of the dialogs</li>
</ol>

<p>Now sign your application</p>

<code>codesign -s "My Certificate" -f $(which python)</code>

<p>In the dialog that appears, click "Allow".</p>

<p>Note that when using a virtual environment, you need to activate the virtual environment before running this command.</p>