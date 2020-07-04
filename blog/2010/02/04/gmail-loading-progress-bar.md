<code name="html">
&lt;!doctype html>
&lt;html>
&lt;head>
	&lt;meta http-equiv="content-type" content="text/html; charset=UTF-8">
	&lt;title>&lt;/title>
	&lt;style type="text/css">
	body {
		margin: 0;
		width: 100%;
		height: 100%
	}
	body,td,input,textarea,select {
		font-family: arial,sans-serif
	}
	input,textarea,select {
		font-size: 100%
	}
	#loading {
		position: absolute;
		width: 100%;
		height: 100%;
		z-index: 1000;
		background-color: #fff
	}
	.cmsg {
		margin: 1em
	}
	.msg {
		font-weight: bold
	}
	.lpb {
		margin: 2px 0;
		border: 1px solid #949dad;
		width: 300px;
		height: 0.5em;
		overflow: hidden;
		padding: 1px
	}
	#lpt {
		background: #d4e4ff;
		width: 0;
		height: 100%;
		font-size: 0
	}
	.invfr {
		position: absolute;
		left: 0;
		top: 0;
		z-index: -1;
		width: 0;
		height: 0;
		border: 0
	}
	.msgb {
		position: absolute;
		right: 0;
		bottom: 10px;
		font-size: 12px;
		font-weight: normal;
		color: #000;
		background: #fff;
		padding: 20px
	}
	&lt;/style>
&lt;/head>
&lt;body>
	&lt;div id="loading" style="">
		&lt;div class="cmsg">
			&lt;div class="msg">
			Loading user@gmail.com&hellip;
			&lt;/div>
			&lt;div class="lpb">
				&lt;div id="lpt" style="width: 92%;">&lt;/div>
			&lt;/div>
		&lt;/div>
		&lt;div class="msgb" id="stb">
			Loading standard view | &lt;a href="">Load basic HTML&lt;/a> (for slow connections)
		&lt;/div>
		&lt;div style="clear: left;" class="cmsg" id="loadingError">
			&lt;p style="font-size: larger; margin: 40px 0pt;">
				This is taking longer than usual.
				&lt;a onclick="" href="">&lt;b>Try reloading the page&lt;/b>&lt;/a>.
			&lt;/p>
			&lt;div>
				If that doesn't work, you can:
				&lt;ol>
					&lt;li>&lt;a href="">Disable Labs and try again&lt;/a>.&lt;/li>
					&lt;li>If you're on a slow connection, try &lt;a href="">basic HTML view&lt;/a>.&lt;/li>
					&lt;li>For more troubleshooting tips, visit the &lt;a href="">help center&lt;/a>.&lt;/li>
				&lt;/ol>
			&lt;/div>
		&lt;/div>
	&lt;/div>
&lt;/body>
&lt;/html>
</code>