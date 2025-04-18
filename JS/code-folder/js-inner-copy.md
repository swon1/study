### 📌 Javascript InnerHTML Copy
<br>

##### ▪ clipboard를 사용한 코드로 localhost / https 환경에서만 사용 가능

```HTML
<div class="con-copy">
    <!-- 코드 복사 영역 -->
    <a href="#none" class="btn"></a>
    <script type="text/javascript">
        event.preventDefault();
    </script>
    <!-- // 코드 복사 영역 -->
</div>
<button type="button" class="btn-con-copy" data-copy="copy">코드 복사</button>
```

```HTML
<script>
    let copyBtn = a.querySelectorAll('.btn-con-copy');
    
    [].forEach.call( copyBtn, ( el ) => {
        el.addEventListener('click', (e) => {
            let $copyDate = (e.target).getAttribute('data-copy');
            // 앞 뒤 여백 없애기 :: .trim();
            let $copyTarget = a.querySelector('.con-'+$copyDate).innerHTML;
            window.navigator.clipboard.writeText($copyTarget).then(() => {
                alert("복사되었습니다.");
            });
        });
    });
</script>
```
