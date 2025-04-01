### 📌 Javascript Toggle Class
<br>

```HTML
<script>
  const btn = document.querySelectorAll('element');
    
    function toggleClass ( element, className ) {
        if ( element.classList.contains( className ) ) {
            element.classList.remove( className );
        } else {
            element.classList.add( className );
        };
    }
    [].forEach.call( btn, ( el ) => {
        el.addEventListener( 'click', (e) => {
            toggleClass( (e.target), 'check' );
        });
    });
</script>
```
