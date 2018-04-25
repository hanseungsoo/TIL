# Javascript - 함수
>하나의 로직을 재실행 할 수 있도록 하는 것. 코드의 재사용성을 높여준다.  

## 함수의 형식
함수는 아래와 같이 구성 된다.
```
function 함수명([인자...[,인자]]){  // 인자가 여러개 올 수 있다.
  코드
  return 반환값  // 값을 반환 할 수 있다.
}
```
## 함수의 정의와 호출
함수를 호출하는 방법은 아래와 같다.
```
function numbering(){  // 숫자 1을 찍는 함수 numbering 정의
  console.log(1);
}

numbering();  // 함수 numbering 호출( ()괄호가 있기에 함수로 인식)
numbering();  // 여러번 사용 가능
```

## 함수의 효용성
>코드의 재사용성은 아주 중요하다. 복잡한 코드가 여러번 사용해야 될 경우 이것을 함수 하나로 정의하여 여러군데에서 호출하는 것이 바람직 할 것이다.

- 재사용성
- 유지보수의 용이
- 가독성
함수를 사용하여 얻는 이득이다.
```
var i = 0;
while(i < 20){
  console.log(i);
}
```
숫자를 찍는 위 코드를 사용하려고 한다. 만약 함수가 없다면 저 코드를 매번 적어줘야 할 것이다. 그것 자체도 힘들 것인데.. 만약 20번 loop도는 것을 30번으로 고친다면? 코드를 적어 준 곳마다 20을 30으로 고쳐야 한다. 이것보다는 함수를 사용한다면 함수 정의부 한 곳만 수정하면 해결 될 것이다.  
함수를 사용함으로써 얻는 이득은 똑같은 코드를 쓰지 않아도 되는 것도 있지만 코드가 수정될때도 많은 이득을 준다.  

## 함수의 출력
>함수는 'return' 키워드를 통해 함수 호출자에게 응답을 줄 수 있다.
```
function get_member1(){
  return 'egoing';   // return 명령을 통해 출력값을 호출한 곳으로 넘겨줌
}

function get_member2(){
  return 'k8805';
}
console.log(get_member1());  // 함수의 return 값인 'egoing'이 출력
console.log(get_member2());  // 함수의 return 값인 'k8805'이 출력
```
함수에는 return이 여러개 올 수 도 있는데 return을 하나라도 만나게 되면 함수가 끝나게 된다.

## 함수의 입력
>함수에게 특정 값을 전달 할 수 있다.
```
function get_argument(arg){  // arg 라는 변수로 값을 받을 수 있다.
  return arg;  // 변수 arg 출력
}

console.log(get_argument(1));   // 함수에 숫자 1를 전달하고 숫자 1를 전달 받아 출력한다.
console.log(get_argument(2));   // 함수에 숫자 2를 전달하고 숫자 2를 전달받아 출력한다.
```
함수에 전달하는 것들을 인자라고 하는데 이 인자는 여러개가 될 수 있다. 
```
function get_arguments(arg1, arg2){  // 인자를 2개 받는다.
  return arg1 + arg2;   // 인자 두개를 더한 값을 출력
}
```
이러한 기능을 이용하여 특정 값을 전달받아 함수 내에서 사용한 후 특정 값으로 되돌려주는 형태로 사용하게 된다.

## 함수를 정의하는 다른 방법
- 변수에 함수 정의
```
var numbering = function(){  // numbering이라는 변수에 함수를 넣어줌
  console.log('egoing');
}

numbering();  // 변수 뒤에 ()기호를 이용하여 함수 호출
```
- 즉시 실행 함수(익명 함수)
```
(function(){
   console.log('egoing');
 }
)();  // 함수를 ()로 감싼 후 ()기호를 이용하여 호출 한다.
