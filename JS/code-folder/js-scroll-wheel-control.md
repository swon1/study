### 📌 Javascript Scroll Wheel Control
<br>

```HTML
<script>
    // Wheel Event One Page
    const onePage = () => {
        let boxA = a.querySelectorAll('.pageA .page-unit');
        let total = boxA.length - 1;
        let idx = 0;
        let motion;
    
        function pageUp () {
            let preidx = idx;
            if ( idx <= 0 ) {
                motion = false;
                idx = 0;
                return false;
            } else {
                setTimeout(() => { motion = false; },200);
                idx--;
            }
        }
        function pageDown () {
            let preidx = idx;
            if ( idx >= total ) {
                motion = false;
                idx = total;
                return false;
            } else {
                setTimeout(() => { motion = false; },200);
                idx++;
            }
        }
    
        // pc Wheel Event
        function wheelP () {
            Array.prototype.forEach.call( boxA, ( el ) => {
                el.addEventListener('wheel', ( event ) => {
                    event.preventDefault();
                    let wCheck = event.wheelDelta;
    
                    // console.log(event);
                    // console.log(event.wheelDelta);
    
                    if ( !(motion) ) {
                        motion = true;
                        if ( wCheck > 0 ) {
                            pageUp();
                        } else {
                            pageDown();
                        }
                    } else {
                        return false;
                    }
                },{ passive : false });
            })
        }
    
        // mobile Touch Event
        function touchP () {
            let $touchS, $touchE;
            Array.prototype.forEach.call( boxA, ( el ) => {
                el.addEventListener('touchstart', ( evt ) => {
                    evt.preventDefault();
                    $touchS = evt.touches[0].pageY;
                });
                el.addEventListener('touchend', ( evt ) => {
                    evt.preventDefault();
                    $touchE = evt.changedTouches[0].pageY;
    
                    if ( !(motion) ) {
                        motion = true;
                        if ( $touchS > $touchE ) {
                            pageDown();
                        } else {
                            pageUp();
                        }
                    } else {
                        return false;
                    }
                });
            });
        }
        wheelP();
        touchP();
    }
    onePage();
</script>
```
