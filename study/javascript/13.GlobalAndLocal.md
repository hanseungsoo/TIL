# Javascript - 유효범위
> 유효범위는 변수의 수명을 의미

## 전역변수
> 자바스크립트 어플리케이션에서 접근할 수 있는 변
```
var vscope = 'global';
function fscope(){
  console.log(vscope); // 함수 안에 없다면 밖에 있는 변수에 접근
}

fscope();  // global 출력
```

## 지역변수
> 
```
var vscope = 'global';
function fscope(){
  var vscope = 'local';
  console.log(vscope);  // 함수 내의 변수에 접근
}

fscope();  // local 출력
```

## 전역변수와 지역변수
```
var vscope = 'global';  // 함수 밖이면 전역변수
function fscope(){
  var vscope = 'local';  // 함수 아니면 지역변수
  vscope = 'local';  // 로컬변수가 없다면 전역변수를 의미
}
fscope();
```

## 전역변수를 사용하는 법
> 전역변수 사용을 지양한다. 어쩔수 없이 필요하다면 사용을 최소화 한다.
```
# 객체하나를 전역변수로 만들고 관리하기
MYAPP = {}
MYAPP.calculator = {
    'left' : null,
    'right' : null
}
MYAPP.coordinate = {
    'left' : null,
    'right' : null
}
 
MYAPP.calculator.left = 10;
MYAPP.calculator.right = 20;
function sum(){
    return MYAPP.calculator.left + MYAPP.calculator.right;
}
document.write(sum());

# 익명함수로 만들어 함수의 로컬변수로 사용
(function(){
    var MYAPP = {}
    MYAPP.calculator = {
        'left' : null,
        'right' : null
    }
    MYAPP.coordinate = {
        'left' : null,
        'right' : null
    }
    MYAPP.calculator.left = 10;
    MYAPP.calculator.right = 20;
    function sum(){
        return MYAPP.calculator.left + MYAPP.calculator.right;
    }
    document.write(sum());
}())
```
## 유효범위의 대상
> 자바스크립트에서는 함수를 기준으로 지역변수를 구분 짓는다.
```
for(var i = 0; i < 1; i++){
  var name = 'coding everybody';  // 일반적인 자바문법이라면 for문을 탈출 하면 name을 사용할 수 없다.
}

console.log(name); // 제대로 출력된다.
```

## 정적 유효범위
> 
```
var i = 5;  // 전역변수

function a(){
  var i = 10;  // 지역변수
  b();
}

function b(){
  console.log(i);  // 5 출력
}

a();
```
함수 b가 선언될때 전역변수 i를 찾는다. 이러한 것을 정적 유효범위라고 한다.

