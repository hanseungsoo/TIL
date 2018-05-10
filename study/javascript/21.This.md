# 자바스크립트 - this
> this는 함수내에서 함수 호출 맥락(context)를 의미한다. 함수를 어떻게 호출하느냐에 따라서 this가 가르키는 대상이 달라진다.

## 함수와 this
```
function func(){
  if(window === this){  
    console.log("window === this");
  }
}
func();  // window === this 출력 -> this에 전역 객체가 할당
```
func함수는 window 전역객체에 소속하고 있기 때문에 this는 window 전역 객체가 된다.
## 메소드와 this
```
var o = {
  func : function(){
    if(o === this){
      console.log("o === this");
    }
  }
}
o.func();
```
객체의 소속인 메소드의 this는 그 객체를 가르킨다.

## 생성자와 this
```
var funcThis = null;
function Func(){
  funcThis = this;  // var을 붙이지 않았기 때문에 전역 변수를 가르키는 funcThis
}

var o1 = Func();  // 함수로 실행
if(funcThis === window){
  console.log('window');
}

var o2 = new Func();  // 생성자로 사용
if(funcThis === o2){ 
  console.log('o2');
}
```
어떠한 함수를 함수로 사용할때와 생성자로 사용될때와 this에 차이가 난다는 것을 명심해야 된다. 생성자로 사용할때 this가 필요한 이유는 생성자 함수 내에서 객체가 만들어지기 전에 해당 객체를 참조할 수 있는 유일한 방법이기 때문이다.

## apply와 this
함수의 메소드인 apply, call를 이용하면 this의 값을 제어 할 수 있다.
```
var o = {}
var p = {}

function func(){
  switch(this){
    case o:
      console.log('o');
      break;
    case p:
      console.log('p');
      break;
    case window:
      console.log('window');
      break;
  }
}
func();  // window 실행
func.apply(o);  // o 실행
func.apply(p);  // p 실행
```
