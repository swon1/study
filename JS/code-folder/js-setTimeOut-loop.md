### 📌 Javascript SetTimeOut Infinite Function
<br>

```HTML
<script>
    let $initial = 0;
    let $unit = a.querySelectorAll('element');
    
    const startFn = function ( e ) {
        setTimeout( function () {
            setFn( e );
        }, 1500);
    };
    const setFn = function ( n ) {
        let $unitL = $unit.length;
        if ( n < ($unitL-1) ) {
            n++;
        } else if ( n == ($unitL-1) ) {
            n = 0;
        }
        startFn( n );
    };
    setFn( $initial );
</script>
```
