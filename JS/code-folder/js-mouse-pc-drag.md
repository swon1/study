### 📌 Javascript Mouse PC Drag

##### 💡 [Demo View](https://swon1.github.io/study/demo/js/js-mouse-drag.html)
<br>

```HTML
<div class="nav_inner mouseScroll"> <!-- 구조 -->
  <ul>
    <li><button type="button">null</button></li>
    <li><button type="button">null</button></li>
    <li><button type="button">null</button></li>
  </ul>
</div>
```
```CSS
  .nav_inner {width:500px;height:100px;overflow-x:scroll;}
  .nav_inner::-webkit-scrollbar {display:none;}
  .nav_inner ul {display:flex;flex-wrap:wrap;flex-direction:row;width:150%;height:100%;}
```
```Javascript
  let isDown = false;
  const mouseScroll = function ( ele ) {
    const scrollTarget = ele;
    let startX;
    let scrollLeft;
  
    const scrollStartFn = function (e) {
      scrollTarget.classList.add('active');
      startX = e.pageX - scrollTarget.offsetLeft;
      scrollLeft = scrollTarget.scrollLeft;
      window.addEventListener('mousemove',scrollMoveFn);
      window.addEventListener('mouseup',scrollEndFn);
    };
    const scrollMoveFn = function (e) {
      isDown = true;
      const x = e.pageX - scrollTarget.offsetLeft;
      const walk = x - startX;
      scrollTarget.scrollLeft = scrollLeft - walk;
    };
    const scrollEndFn = function (e) {
      scrollTarget.classList.remove('active');

      window.removeEventListener('mousedown',scrollStartFn);
      window.removeEventListener('mousemove',scrollMoveFn);
      window.removeEventListener('mouseup',scrollEndFn);

      setTimeout(function(){
        isDown = false;
      },50);
    };
    const eventFn = function () {
      scrollTarget.addEventListener('mousedown',scrollStartFn);
    };
    eventFn();
  };
  
  const multiScroll = function ( ele ) {
    const scrollTarget = ele;
    let startX;
    let scrollLeft;
    let moved;
    let tarEl;
  
    const scrollStartFn = function (el,e) {
      el.classList.add('active');
      startX = e.pageX - el.offsetLeft;
      scrollLeft = el.scrollLeft;
      moved = true;
      window.addEventListener('mousemove', (e) => { scrollMoveFn(el,e) });
      window.addEventListener('mouseup', (e) => { scrollEndFn(el,e) });
    };
    const scrollMoveFn = function (el,e) {
      if ( !moved ) { return; }
      el = tarEl;
      isDown = true;
      const x = e.pageX - el.offsetLeft;
      const walk = x - startX;
      el.scrollLeft = scrollLeft - walk;
    };
    const scrollEndFn = function (el,e) {
      tarEl.classList.remove('active');

      window.removeEventListener('mousemove',scrollMoveFn);
      window.removeEventListener('mouseup',scrollEndFn);
      el.removeEventListener('mousedown',scrollStartFn);

      moved = false;

      setTimeout(function(){
        isDown = false;
      },50);
    };
    const eventFn = function () {
      [].forEach.call( scrollTarget, ( el ) => {
        el.addEventListener('mousedown', (e) => {
          tarEl = el;
          scrollStartFn(tarEl,e);
        });
      });
    };
    eventFn();
  };
  
  let btn = document.quarySelectorAll('.nav_inner button');
  [].forEach.call( btn, ( el ) => {
      el.addEventListener( 'click', (e) => {
          // 드래그 기능 중 클릭 방지 (마우스 엔터 방지)
          if ( isDown == false ) {
            console.log('드래그가 끝난 후');
          }
      });
  });
  
  // 단독일 경우
  const scrollEl = document.querySelector('.mouseScroll');
  mouseScroll( scrollEl );
  
  // 여러개일 경우
  const scrollmEl = document.querySelectorAll('.mouseScroll');
  multiScroll( scrollmEl );
```
