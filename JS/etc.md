# 📋 JavaScript 코드 및 팁
<br>

#### 📌 삼항연산자
```Javascript
    // $time 변수가 1 일경우 오후, 0 일경우 오전
    
    let $time;
    ( $time >= 1 ) ? console.log('오후') : console.log('오전');
```
##### ▪ ( 조건 ) ? 참일경우 반환값 : 거짓일경우 반환값<br>
반환값에는 수식,함수 등 여러 가지 형태의 명령문이 올 수 있다.
<br><br>

#### 📌 toggle (토글) 클래스 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-toggle-class.md)
<br>

#### 📌 SetTimeOut을 이용한 반복 코드 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-setTimeOut-loop.md)
<br>

#### 📌 태그 내부 내용 복사 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-inner-copy.md)
<br>

#### 📌 랜덤 숫자 추출
```Javascript
    let number = Math.floor(Math.random() * 100) + 1;
```
##### ▪ 프로그래밍 숫자는 0 부터 시작하기때문에 1~N 수를 추출하려면 끝에 +1 을 더해준다.
<br>

#### 📌 랜덤 숫자 반복적으로 추출 중 같은 숫자 방지 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-random-no-same.md)














