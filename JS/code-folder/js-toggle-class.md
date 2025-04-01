### 📌 Javascript Toggle Class
<br>

▪ 'btn' 변수에 원하는 요소를 반영한다.

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
