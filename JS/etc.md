# 📋 JavaScript 코드 및 팁

<br><br>

#### 📌 삼항연산자
##### ▪ ( 조건 ) ? 참일경우 반환값 : 거짓일경우 반환값<br>
 반환값에는 수식,함수 등 여러 가지 형태의 명령문이 올 수 있다.
```Javascript
  // $time 변수가 1 일경우 오후, 0 일경우 오전

  let $time;
  ( $time >= 1 ) ? console.log('오후') : console.log('오전');
```

<br><br>

#### 📌 랜덤 숫자 추출
```Javscript
  number = Math.floor(Math.random() * 6) + 1;
```
