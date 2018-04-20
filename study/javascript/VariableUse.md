# Javascript - 변수
>변수는 값이 바뀔 수 있는 그릇으로 값을 담는 컨테이너이다.  
사람의 언어로는 대명사로 볼 수 있다.

## 변수의 사용법
자바스크립트에서 변수는 'var'로 선언한다.
```
var a = 1;      // 변수 a 선언
console.log(a); // 숫자 1 출력

a = 10;         // 한번 선언된 변수는 값을 변경 가능하며 var를 붙이지 않는다.
console.log(a)  // 숫자 10 출력
```
'var'를 생략할 수 있다고 하는데 유효범위와 관련해서 영향을 받는 부분이 있어 명확하게 알기전까진 'var'를 사용하는 것이 좋다.

변수끼리 연산도 가능하다.
```
var a = 1;
var b = 2;

console.log( a + b );   // 숫자 3 출력
console.log( a + 1 );   // 숫자 2 출력
```
변수에는 숫자만 들어 갈 수 있는 것은 아니다. 문자도 가능하다
```
var a = 'coding';
console.log(a);  // 문자열 conding 출력

console.log( a + ' everybody' ); // 문자열 coding everybody 출력
```

## 변수의 효용
변수는 코드의 재활용성을 높여준다.
```
console.log(100+10);
console.log((100+10) / 10);
console.log(((100+10) / 10) - 10);
console.log((((100+10) / 10) - 10) * 10);
위와 같은 코드에서 100을 다른 값으로 바꾸려면 모든 코드의 값을 바꿔줘야 한다.  
100을 변수로 설정하여 사용하면 많은 수정이 필요하지 않는다.

var a = 100;
a = a + 10;
console.log(a);   //  100 + 10 결과
a = a / 10;
console.log(a);   //  (100 + 10) / 10 결과
a = a - 10;
console.log(a);   //  ((100 + 10) / 10) - 10 결과
100을 변경 하고 싶으면 맨위의 'var a = 100'코드면 값을 바꾸어주면 모든 코드에 적용이 된다.
````

## 참고 내용
<https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Values,_variables,_and_literals>

