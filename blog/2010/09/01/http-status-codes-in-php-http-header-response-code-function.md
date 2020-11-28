Output your desired HTTP status code using the status code and the `header()` function.

```php
function HTTPStatus($num) {
    $http = array(
        100 => 'HTTP/1.1 100 Continue',
        101 => 'HTTP/1.1 101 Switching Protocols',
        200 => 'HTTP/1.1 200 OK',
        201 => 'HTTP/1.1 201 Created',
        202 => 'HTTP/1.1 202 Accepted',
        203 => 'HTTP/1.1 203 Non-Authoritative Information',
        204 => 'HTTP/1.1 204 No Content',
        205 => 'HTTP/1.1 205 Reset Content',
        206 => 'HTTP/1.1 206 Partial Content',
        300 => 'HTTP/1.1 300 Multiple Choices',
        301 => 'HTTP/1.1 301 Moved Permanently',
        302 => 'HTTP/1.1 302 Found',
        303 => 'HTTP/1.1 303 See Other',
        304 => 'HTTP/1.1 304 Not Modified',
        305 => 'HTTP/1.1 305 Use Proxy',
        307 => 'HTTP/1.1 307 Temporary Redirect',
        400 => 'HTTP/1.1 400 Bad Request',
        401 => 'HTTP/1.1 401 Unauthorized',
        402 => 'HTTP/1.1 402 Payment Required',
        403 => 'HTTP/1.1 403 Forbidden',
        404 => 'HTTP/1.1 404 Not Found',
        405 => 'HTTP/1.1 405 Method Not Allowed',
        406 => 'HTTP/1.1 406 Not Acceptable',
        407 => 'HTTP/1.1 407 Proxy Authentication Required',
        408 => 'HTTP/1.1 408 Request Time-out',
        409 => 'HTTP/1.1 409 Conflict',
        410 => 'HTTP/1.1 410 Gone',
        411 => 'HTTP/1.1 411 Length Required',
        412 => 'HTTP/1.1 412 Precondition Failed',
        413 => 'HTTP/1.1 413 Request Entity Too Large',
        414 => 'HTTP/1.1 414 Request-URI Too Large',
        415 => 'HTTP/1.1 415 Unsupported Media Type',
        416 => 'HTTP/1.1 416 Requested Range Not Satisfiable',
        417 => 'HTTP/1.1 417 Expectation Failed',
        500 => 'HTTP/1.1 500 Internal Server Error',
        501 => 'HTTP/1.1 501 Not Implemented',
        502 => 'HTTP/1.1 502 Bad Gateway',
        503 => 'HTTP/1.1 503 Service Unavailable',
        504 => 'HTTP/1.1 504 Gateway Time-out',
        505 => 'HTTP/1.1 505 HTTP Version Not Supported',
    );
    
    header($http[$num]);
    
    return array(
        'code' => $num,
        'error' => $http[$num],
    );
}
```

---

Posted Sep 1, 2010.

https://www.darklaunch.com/2010/09/01/http-status-codes-in-php-http-header-response-code-function.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Feb 15, 2011
            <div>
                <p>Very nice post, good luck! ;-)</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Feb 17, 2012
            <div>
                <p>Hi, </p><p></p><p>I think you should actually test to see if the SERVER_PROTOCOL is 1.0 or 1.1. I think the code should be like this: </p><p></p><p>function HTTPStatus($num) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$http_protocol = "HTTP/1.0"; </p><p>&nbsp;&nbsp;&nbsp;&nbsp;if(isset($_SERVER['SERVER_PROTOCOL']) &amp;&amp; stripos($_SERVER['SERVER_PROTOCOL'],"HTTP") &gt;= 0){</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$http_protocol = $_SERVER['SERVER_PROTOCOL']; </p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$http = array(</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;100 =&gt; $http_protocol . ' 100 Continue',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;101 =&gt; $http_protocol . ' 101 Switching Protocols',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;200 =&gt; $http_protocol . ' 200 OK',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;201 =&gt; $http_protocol . ' 201 Created',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;202 =&gt; $http_protocol . ' 202 Accepted',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;203 =&gt; $http_protocol . ' 203 Non-Authoritative Information',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;204 =&gt; $http_protocol . ' 204 No Content',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;205 =&gt; $http_protocol . ' 205 Reset Content',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;206 =&gt; $http_protocol . ' 206 Partial Content',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;300 =&gt; $http_protocol . ' 300 Multiple Choices',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;301 =&gt; $http_protocol . ' 301 Moved Permanently',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;302 =&gt; $http_protocol . ' 302 Found',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;303 =&gt; $http_protocol . ' 303 See Other',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;304 =&gt; $http_protocol . ' 304 Not Modified',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;305 =&gt; $http_protocol . ' 305 Use Proxy',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;307 =&gt; $http_protocol . ' 307 Temporary Redirect',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;400 =&gt; $http_protocol . ' 400 Bad Request',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;401 =&gt; $http_protocol . ' 401 Unauthorized',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;402 =&gt; $http_protocol . ' 402 Payment Required',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;403 =&gt; $http_protocol . ' 403 Forbidden',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;404 =&gt; $http_protocol . ' 404 Not Found',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;405 =&gt; $http_protocol . ' 405 Method Not Allowed',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;406 =&gt; $http_protocol . ' 406 Not Acceptable',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;407 =&gt; $http_protocol . ' 407 Proxy Authentication Required',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;408 =&gt; $http_protocol . ' 408 Request Time-out',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;409 =&gt; $http_protocol . ' 409 Conflict',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;410 =&gt; $http_protocol . ' 410 Gone',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;411 =&gt; $http_protocol . ' 411 Length Required',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;412 =&gt; $http_protocol . ' 412 Precondition Failed',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;413 =&gt; $http_protocol . ' 413 Request Entity Too Large',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;414 =&gt; $http_protocol . ' 414 Request-URI Too Large',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;415 =&gt; $http_protocol . ' 415 Unsupported Media Type',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;416 =&gt; $http_protocol . ' 416 Requested Range Not Satisfiable',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;417 =&gt; $http_protocol . ' 417 Expectation Failed',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;500 =&gt; $http_protocol . ' 500 Internal Server Error',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;501 =&gt; $http_protocol . ' 501 Not Implemented',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;502 =&gt; $http_protocol . ' 502 Bad Gateway',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;503 =&gt; $http_protocol . ' 503 Service Unavailable',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;504 =&gt; $http_protocol . ' 504 Gateway Time-out',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;505 =&gt; $http_protocol . ' 505 HTTP Version Not Supported',</p><p>&nbsp;&nbsp;&nbsp;&nbsp;);</p><p> </p><p>&nbsp;&nbsp;&nbsp;&nbsp;header($http[$num]);</p><p> </p><p>&nbsp;&nbsp;&nbsp;&nbsp;return</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;array(</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'code' =&gt; $num,</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'error' =&gt; $http[$num],</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;);</p><p>}</p><p></p><p>Cheers, </p><p>Thusjanthan Kubendranathan</p>
            </div>
        </div>
    </li>
</ol>
