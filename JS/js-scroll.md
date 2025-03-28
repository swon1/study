# 📋 JavaScript - Scroll
### 🧷 JS 스크롤 관련된 코드
<br>

#### 📌 각 섹션영역 감지
```Javascript
    // section - scroll - animated - js
    b.addEventListener('scroll',function(e){
        let $scrollArea = a.querySelectorAll('.section-scroll-area');
        
        for ( i=0; i<$scrollArea.length; i++ ) {
            let $el = $scrollArea[i];
            let $elTop = $el.getBoundingClientRect().top;
            let $elClass = $el.classList.contains('active');
            
            if ( $elTop <= (b.innerHeight) || $elClass ) { $el.classList.add('active'); }
        }
    });
```
