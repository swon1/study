### 📌 Javascript Random No Same Number
<br>

```HTML
<script>
    const setChangeImg = function () {
        const setRNum = function ( beNum ) {
            let $randomNum = Math.floor(Math.random() * 9) + 1;
    
            while ( beNum == $randomNum ) {
                $randomNum = Math.floor(Math.random() * 9) + 1;
            }
            startFn($randomNum);
        }
        const startFn = function ( num ) {
            setTimeout( function () {
                setRNum( num );
            },1000);
        }
        setRNum(1);
    };
    setChangeImg();
</script>
```
