## 📋 JavaScript 코드 및 팁
<br>

#### 📌 배열 내 같은 요소 제거 - set
```Javascript
    const names = ['kim', 'Lee', 'Park', 'Lee', 'Kim'];
    const uniqueNamesWithArrayFrom = Array.from(new Set(names));
    const uniqueNamesWithSpread = [...new Set(names)];
```
<br>

#### 📌 단순 true 조건의 if 문을 사용할때는 && 연산자를 통해 간결하게 작성 가능
##### ▪ 반대의 경우에는 || 연산자를 사용
```Javascript
    if ( $active ) { console.log('GO'); }
    
    $active && console.log('GO');
```
<br>

#### 📌 삼항연산자
##### ▪ ( 조건 ) ? 참일경우 반환값 : 거짓일경우 반환값<br>
```Javascript
    // $time 변수가 1 일경우 오후, 0 일경우 오전
    
    let $time;
    ( $time >= 1 ) ? console.log('오후') : console.log('오전');
```
<br>

#### 📌 toggle 토글 클래스 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-toggle-class.md)

#### 📌 toggle Slide 토글 슬라이드 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-toggle-slide.md) - [Demo View](https://swon1.github.io/study/demo/js/js-toggle-slide.html)

#### 📌 SetTimeOut을 이용한 반복 코드 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-setTimeOut-loop.md)

#### 📌 태그 내부 내용 복사 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-inner-copy.md)
<br>

#### 📌 랜덤 숫자 추출
##### ▪ 프로그래밍 숫자는 0 부터 시작하기때문에 1~N 수를 추출하려면 끝에 +1 을 더해준다.
```Javascript
    let number = Math.floor(Math.random() * 100) + 1;
```
<br>

#### 📌 랜덤 숫자 반복적으로 추출 중 같은 숫자 방지 - [Code View](https://github.com/swon1/study/blob/master/JS/code-folder/js-random-no-same.md) - [Demo View](https://swon1.github.io/study/demo/js/js-random-number.html)














