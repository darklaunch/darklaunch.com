<p>Wrap jQuery next and prev functions with $.nextWrap() and $.prevWrap().</p>

<code name="javascript">
(function( $ ) {
    $.fn.nextWrap = function( selector ) {
        var $next = $(this).next( selector );

        if ( ! $next.length ) {
            $next = $(this).parent().children( selector ).first();
        }

        return $next;
    };

    $.fn.prevWrap = function( selector ) {
        var $previous = $(this).prev( selector );

        if ( ! $previous.length ) {
            $previous = $(this).parent().children( selector ).last();
        }

        return $previous;
    };
})( jQuery );
</code>

<p>Given the following markup:</p>
<code name="html">
<ul>
    <li class="one"></li>
    <li class="two"></li>
    <li class="three"></li>
</ul>
</code>

<p>These all evaluate to true.</p>

<code name="javascript">
&lt;script>
console.log( $( '.one' ).nextWrap().is( '.two' ) ); // true
console.log( $( '.two' ).nextWrap().is( '.three' ) ); // true
console.log( $( '.three' ).nextWrap().is( '.one' ) ); // true

console.log( $( '.three' ).prevWrap().is( '.two' ) ); // true
console.log( $( '.two' ).prevWrap().is( '.one' ) ); // true
console.log( $( '.one' ).prevWrap().is( '.three' ) ); // true
</script>
</code>