# Javascript - 모듈
>코드의 재활용성을 높이고, 유지보수를 쉽게 할 수 있는 기법들 중하나가 파일을 분리하여 각 파일들을 모듈화 시키는 것이다.

- 자주 사용되는 코드를 별도의 파일로 만들어 두면 필요할 때마다 재활요 할 수 있음
- 코드 수정 시에 필요한 로직을 빠르게 찾을 수 있음
- 필요한 로직만을 로드해서 메모리의 낭비를 줄일 수 있음
- 코드를 개선하면 이것을 가져다 쓰고 있는 애플리케이션이 모두 개선 됨
- 사용되었던 모듈은 다시 네트워크를 통해 다운받지 않기 때문에 속도 개선 효과

## 모듈화 (웹브라우저)
```
# main.html
<html>
<head>
  <meta charset="utf-8"/>
  <script src="greeting.js"></script>  // greeting.js 
</head>
<body>
  <script>
    alert(welcome());  // greeting.js 에 정의되어 있는 함수를 호출할 수 있다.
  </script>
</body>
</html>
  
# greeting.js -> 이 파일을 여러 html 파일에서 사용할 수 있다.
function welcom(){
  return 'Hello World';
}
```

## 모듈화 (node.js)
```
# node.circle.js (로드될 대상)
var PI = Math.PI;
exports.area = fucntion(r){
  return PI * r * r;
};

exports.circumference = function(r){
  return 2 * PI * r;
};

# node.demo.js (모듈을 로드하는 측)
var circle = require('./node.circle.js');  // node.js에서 제공하는 require기능으로 모듈을 로드
console.log( circle.area(4) );
```

## 라이브러리
>라이브러리는 개발을 진행할때 좀 더 간편하고 쉽게 구현을 하기 위해 미리 기능들을 구성하여 묶어놓은 기능 묶음이다.
라이브러리를 사용하지 않아도 직접 구현할 수도 있으나 그렇게하려면 많은 공수가 들어가게 된다.

