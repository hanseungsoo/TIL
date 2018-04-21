# Javascript - 비교
>값과 값이 있을때 두개의 값이 같은지, 어느쪽이 큰지 비교

## 연산자
>어떤 작업을 컴퓨터에게 지시하기 위한 기호

### 대입 연산자(=)
>변수에 어떠한 값을 대입할때 사용
```
a = 1; // a라는 변수에 상수 1을 대입하여라
```

### 비교 연산자(<,<=,=>,>,==)
>주어진 값들이 같은지, 다른지, 큰지, 작은지 구분
비교 연산자의 결과는 true, false인 블린(boolean) 데이터 형으로 나타난다.

- '=='  : 동등 연산자
>좌항과 우항을 비교하여 서로 값이 같다면 true 다르면 false
- '===' : 일치 연산자(동등 연산자보다는 일치 연산자를 권장)
>좌항과 우항이 '정확'하게 같을때 true 다르면 false  
여기서 '정확'이란 값뿐만 아니라 데이터 타입까지 같은 것.
```
alert(1 === "1")  // false 똑같은 1이지만 엄격하게 한다면 숫자 1과 문자 1이다.
alert(2 == "1")   // true 데이터가 똑같은 1이다.
alert(null == undefined) // true
alert(null === undefined)  // false
alert(true == 1)  // true
alert(true === 1) // false
alert(true == '1')  // true
alert(true === '1') // false
alert(0 === -0)  // true
alert(NaN === NaN)  // false (NaN은 계산할 수 없음)
```
'=='와 '==='의 차이점 참조 <https://dorey.github.io/JavaScript-Equality-Table/>
-'!' : 부정(비교 연산자에서 같지 않다를 표현)
-'>' : 좌항이 우항보다 크다면 true, 작다면 false
-'>=' : 좌항이 우항보다 크거나 같다면 true, 작다면 false
