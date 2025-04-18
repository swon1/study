## 📋 HTML 코드 및 팁
<br>

#### 📌 img 태그
▪ `title : 이미지 설명 / alt : 이미지 정보` <br>
▪ 이미지가 내포한 정보가 너무 길 경우 IR(Image Replacement) 처리
##### ▪ 태그 로딩 제어
```HTML
<img src="images.jpg" loading="lazy"> <!-- "auto", "eager", "lazy" -->
```

#### 📌 기본 URL 주소 세팅하기
```HTML
<head>
    <base href="https://github.com/swon1/study" target="_blank" />
</head>
<body>
    <a href="/tree/master/HTML">HTML</a>
    <a href="/tree/master/JS">JS</a>
</body>
```

#### 📌 href 속성에서 이메일이나 연락처로 연동시키기
```HTML
<!-- Email -->
<a href="mailto:name@example.com"> Send Email </a>

<!-- Call -->
<a href="tel:+1234567890"> Call Us </a>

<!-- SMS -->
<a href="sms:+1234567890"> Send SMS </a>
```

#### 📌 텍스트 번역 제어
```HTML
<p translate="yes">
    This is Github Page
</p>
```

#### 📌 맞춤법 검사 여부 제어
```HTML
<input type="text" spellcheck="true" />
```

#### 📌 HTML 특수문자 리스트 - [View](http://kor.pe.kr/util/4/charmap2.htm)
