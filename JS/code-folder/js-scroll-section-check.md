### 📌 Javascript Scroll Section Check

##### 💡 [Demo View](https://swon1.github.io/study/demo/js/js-scroll-sec-check.html)
<br>

```HTML
<script>
    // section - scroll - animated - js
    window.addEventListener('scroll',function(e){
        let $scrollArea = a.querySelectorAll('.section-scroll-area');
        
        for ( i=0; i<$scrollArea.length; i++ ) {
            let $el = $scrollArea[i];
            let $elTop = $el.getBoundingClientRect().top;
            let $elClass = $el.classList.contains('active');
            
            if ( $elTop <= (window.innerHeight) || $elClass ) { $el.classList.add('active'); }
        }
    });
</script>
```
