# Javascript - 조건문
>주어진 조건에 따라서 에플리케이션을 다르게 동작하도록 하는 것

## 조건문의 문법
조건문은 if로 시작하며 if 뒤의 괄호에 조건이 오며 조건이 될 수 있는 값은 Boolean이다.
```
* 중괄호 실행
if(true){
  alert('result : true');
}

* 중괄호 실행 하지 않음
if(false){
  alert('result : true');
}

* else 문
if(true){
  alert(1);  // 실행
} else {
  alert(2);
}

if(false)
  alert(1);
} else {
  alert(2);  // 실행
}

* else if 문
if(false){
  alert(1);
} else if(true) {
  alert(2);  // 실행
} else if(true) {
  alert(3);  // 실행 X
} else {
  alert(4);
}

```

## 변수와 비교연산자
>비교연산자와 변수를 결합하여 if문을 제대로 사용한다.
```
var a = 1;

if(a===1){
   alert(1);  // 수행
}
```

prompt를 사용하여 값을 받을 수 있다.
```
alert(prompt('당신의 나이는?')); // 입력된 값 alert으로 표현
```

위 두개의 기능을 결합하여 사용해보자
```
var id = prompt('아이디를 입력해주세요.');

if( id === 'egoing'){     //  위에서 입력받은 값을 비교 연산자로 비교
   alert('아이디가 일치 합니다.');
} else {
   alert('아이디가 일치하지 않습니다.');
}
```

## 논리 연산자
>조건문을 좀 더 간결하고 다양하게 방법으로 구사할 수 있게함

- && : 좌항과 우항이 모두 true일때 true(참)이 됨
- || : 좌항과 우항 중 하나라도 ture일때 true(참)이 됨

## boolean의 대체제 (쓰지 않는 것이 좋다)
boolean 타입은 종료는 true와 false가 있는데 이것을 대체하는 값이 있다.
- false => 0, '', undefined, null, NaN
- true => 0이 아닌 값들

