# 📋 JavaScript 코드 및 팁
<br>

#### 📌 삼항연산자
##### ▪ ( 조건 ) ? 참일경우 반환값 : 거짓일경우 반환값<br>
반환값에는 수식,함수 등 여러 가지 형태의 명령문이 올 수 있다.
```Javascript
    // $time 변수가 1 일경우 오후, 0 일경우 오전
    
    let $time;
    ( $time >= 1 ) ? console.log('오후') : console.log('오전');
```

#### 📌 toggle (토글) 클래스 - [Code View](https://github.com/swon1/study/blob/main/JS/code-folder/js-toggle-class.md)

#### 📌 SetTimeOut을 이용한 반복 코드
```Javascript
    let $initial = 0;
    let $unit = a.querySelectorAll('element');
    
    const startFn = function ( e ) {
        setTimeout( function () {
            setFn( e );
        }, 1500);
    };
    const setFn = function ( n ) {
        let $unitL = $unit.length;
        if ( n < ($unitL-1) ) {
            n++;
        } else if ( n == ($unitL-1) ) {
            n = 0;
        }
        startFn( n );
    };
    setFn( $initial );
```
<br>

#### 📌 랜덤 숫자 추출
##### ▪ 프로그래밍 숫자는 0 부터 시작하기때문에 1~N 수를 추출하려면 끝에 +1 을 더해준다.
```Javascript
    let number = Math.floor(Math.random() * 100) + 1;
```
<br>

#### 📌 랜덤 숫자 반복적으로 추출 중 같은 숫자 방지
```Javascript
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
```
<br>




