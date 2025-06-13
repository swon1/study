### 📌 Javascript Toggle Class

##### 💡 [Demo View](https://swon1.github.io/study/demo/js/js-toggle-slide.html)
<br>

```HTML
<style type="text/css">
    .toggleBox {display:block;position:relative;width:80%;margin:100px auto;}
    .toggleBox a{text-align:center;font-weight:bold;font-size:14px;display:block;border:none;padding:15px 20px;margin:20px 10px 0 10px;cursor:pointer;background:#ffd000;color:#333;outline:none;transform:scale(1);transition:.4s ease;border-radius:25px;}
    .toggleBox a:hover{transform:scale(1.1);}
    .toggleBox a.triggerToggle{background:#6f9fef;color:#333;text-decoration:none;}
    .toggleBox #target {padding:12.5em 1.5em;background-color:#ffd000;text-align:center;color:#333;font-weight:700;border-radius:0 0 20px 20px;box-sizing:border-box;display:block;width:95%;margin:0 auto;color:#333;}
    .toggleBox #target h3 {max-width:500px;font-size:1.5;margin:0 auto;line-height:1.618;font-weight:regular;}
</style>
<div class="toggleBox">
    <a href="javascript:void(0);" class="triggerToggle">slideToggle</a>
    <div id="target"><h3>SlideToggle / SlideUp / SlideDown</h3></div>
</div>
```
```HTML
<script type="text/javascript">
    (function(a){
        let isAnimating = false;

        let slideUp = (target, duration=500) => {
            if (isAnimating) return;
            isAnimating = true;

            target.style.transitionProperty = 'height, margin, padding';
            target.style.transitionDuration = duration + 'ms';
            target.style.boxSizing = 'border-box';
            target.style.height = target.offsetHeight + 'px';
            target.offsetHeight;
            target.style.overflow = 'hidden';
            target.style.height = 0;
            target.style.paddingTop = 0;
            target.style.paddingBottom = 0;
            target.style.marginTop = 0;
            target.style.marginBottom = 0;
            window.setTimeout( () => {
                target.style.display = 'none';
                target.style.removeProperty('height');
                target.style.removeProperty('padding-top');
                target.style.removeProperty('padding-bottom');
                target.style.removeProperty('margin-top');
                target.style.removeProperty('margin-bottom');
                target.style.removeProperty('overflow');
                target.style.removeProperty('transition-duration');
                target.style.removeProperty('transition-property');
                isAnimating = false;
            }, duration);
        }
        let slideDown = (target, duration=500) => {
            if (isAnimating) return;
            isAnimating = true;

            target.style.removeProperty('display');
            let display = window.getComputedStyle(target).display;

            if (display === 'none')
            display = 'block';

            target.style.display = display;
            let height = target.offsetHeight;
            target.style.overflow = 'hidden';
            target.style.height = 0;
            target.style.paddingTop = 0;
            target.style.paddingBottom = 0;
            target.style.marginTop = 0;
            target.style.marginBottom = 0;
            target.offsetHeight;
            target.style.boxSizing = 'border-box';
            target.style.transitionProperty = "height, margin, padding";
            target.style.transitionDuration = duration + 'ms';
            target.style.height = height + 'px';
            target.style.removeProperty('padding-top');
            target.style.removeProperty('padding-bottom');
            target.style.removeProperty('margin-top');
            target.style.removeProperty('margin-bottom');

            window.setTimeout( () => {
                target.style.removeProperty('height');
                target.style.removeProperty('overflow');
                target.style.removeProperty('transition-duration');
                target.style.removeProperty('transition-property');
                isAnimating = false;
            }, duration);
        }
        let slideToggle = (target, duration = 500) => {
            if (isAnimating) return;

            if (window.getComputedStyle(target).display === 'none') {
                return slideDown(target, duration);
            } else {
                return slideUp(target, duration);
            }
        }
        
        let speedAnimation = 400;
        let targetId = document.getElementById("target");

        let slideBtnClick = (cl, sl) => 
        document.querySelector(cl).addEventListener('click', () => {
            sl(targetId, speedAnimation)
        });

        slideBtnClick('.triggerToggle', slideToggle);
    })(document);
</script>
```
