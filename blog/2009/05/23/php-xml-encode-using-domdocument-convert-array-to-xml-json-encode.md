Encode XML using xml_encode(); similar to json_encode().

```php
function xml_encode($mixed, $domElement=null, $DOMDocument=null) {
    if (is_null($DOMDocument)) {
        $DOMDocument =new DOMDocument;
        $DOMDocument->formatOutput = true;
        xml_encode($mixed, $DOMDocument, $DOMDocument);
        echo $DOMDocument->saveXML();
    }
    else {
        if (is_array($mixed)) {
            foreach ($mixed as $index => $mixedElement) {
                if (is_int($index)) {
                    if ($index === 0) {
                        $node = $domElement;
                    }
                    else {
                        $node = $DOMDocument->createElement($domElement->tagName);
                        $domElement->parentNode->appendChild($node);
                    }
                }
                else {
                    $plural = $DOMDocument->createElement($index);
                    $domElement->appendChild($plural);
                    $node = $plural;
                    if (!(rtrim($index, 's') === $index)) {
                        $singular = $DOMDocument->createElement(rtrim($index, 's'));
                        $plural->appendChild($singular);
                        $node = $singular;
                    }
                }

                xml_encode($mixedElement, $node, $DOMDocument);
            }
        }
        else {
            $domElement->appendChild($DOMDocument->createTextNode($mixed));
        }
    }
}
```

Example:
```php
$data = array();
for ($i = 0; $i < 3; $i++) {
    $data['users'][] = array(
        'name' => 'user' . $i,
        'img' => 'http://www.example.com/user' . $i . '.png',
        'website' => 'http://www.example.com/',
    );
}

header('Content-Type: application/xml');
echo xml_encode($data);

/*
<?xml version="1.0"?>
<users>
  <user>
    <name>user0</name>
    <img>http://www.example.com/user0.png</img>
    <website>http://www.example.com/</website>
  </user>
  <user>
    <name>user1</name>
    <img>http://www.example.com/user1.png</img>
    <website>http://www.example.com/</website>
  </user>
  <user>
    <name>user2</name>
    <img>http://www.example.com/user2.png</img>
    <website>http://www.example.com/</website>
  </user>
</users>
*/
```

json_encode() example for comparison:
```php
header('Content-Type: application/json');
echo json_encode($data);

/*
{
    "users": [{
        "name": "user0",
        "img": "http:\/\/www.example.com\/user0.png",
        "website": "http:\/\/www.example.com\/"
    },
    {
        "name": "user1",
        "img": "http:\/\/www.example.com\/user1.png",
        "website": "http:\/\/www.example.com\/"
    },
    {
        "name": "user2",
        "img": "http:\/\/www.example.com\/user2.png",
        "website": "http:\/\/www.example.com\/"
    }]
}
*/
```

NOTE: for objects use something like:
```php
if (is_object($data)) {
    $data = get_object_vars($data);
}
```

---

Posted May 23, 2009.

https://www.darklaunch.com/2009/05/23/php-xml-encode-using-domdocument-convert-array-to-xml-json-encode.html

---

3 comments

<ol><li><div>

anonymous &ndash; Dec 30, 2010<div>

to account boolean fields, inside the "else" add
$mixed = is_bool($mixed) ? ($mixed ? 'true' : 'false') : $mixed;

        else {
            $mixed = is_bool($mixed) ? ($mixed ? 'true' : 'false') : $mixed;
            $domElement-&gt;appendChild($DOMDocument-&gt;createTextNode($mixed));
        }

</div></div></li><li><div>

anonymous &ndash; Mar 6, 2011<div>

This is great .. the only change I made was:

if (rtrim($index,'s')!==$index &amp;&amp; count($mixedElement)&gt;1) {

Any node ending with 's' was causing an unecessary child node.  (ie: STATUS was  STATUS with a child node STATU)

Thanks again.

</div></div></li><li><div>

anonymous &ndash; Oct 31, 2013<div>

Thanks, it is extremely useful.

</div></div></li></ol>