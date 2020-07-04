<p>Use regular expressions without capturing a group by using non-capturing groups.</p>

<code name="php">
// Page requested is http://www.example.com/en_FR/
$uri = $_SERVER['REQUEST_URI']; // '/en_FR/'

// This regex returns matching groups for parentheses
preg_match('/\/((en|fr|de|it|nl|no|ja)_[A-Z]{2}|jp)\//', $uri, $matches);
$matches = array(
    0 => '/en_FR/',
    1 => 'en_FR',
    2 => 'en'
);

// This regex will include only matching groups using non-capturing groups
// indicated by "?:" inside "()"
preg_match('/\/((?:en|fr|de|it|nl|no|ja)_[A-Z]{2}|jp)\//', $uri, $matches);
$matches = array(
    0 => '/en_FR/',
    1 => 'en_FR'
);
</code>

<code name="php">
// Named groups also supported
preg_match('/\/(?P<locale>(?:en|fr|de|it|nl|no|ja)_[A-Z]{2}|jp)\//', $uri,
    $matches);
$matches = array(
    0 => '/en_FR/',
    'locale' => 'en_FR',
    1 => 'en_FR'
);
</code>

<img alt="" src="/img/uploads/2013-05/regex-named-capture.png" />