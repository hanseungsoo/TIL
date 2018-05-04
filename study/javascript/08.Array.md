# Javascript - 배열
>배열이란 연관된 데이터를 모아서 관리하기 위해 사용하는 데이터 타입이다.

## 배열의 생성
>배열은 대괄호로 시작하여 대괄호로 끝난다. 또한 대괄호 안에 콤마(,)로 구분하여 나열하면 배열이 된다.
```
var member = ['egoing', 'k8805', 'sorialgi'];  // member 변수에 배열 할당
```

하나의 변수에 담은 배열의 내용. 즉 원소들를 변수명 뒤에 대괄호 와 몇 번째 원소인지를 의미하는 인덱스를 사용하여 배열에서 해당 원소를 꺼내온다.
```
var member = ['egoing', 'k8805', 'sorialgi'];

console.log( member[0] );  // egoing 출력
console.log( member[1] );  // k8805 출력
console.log( member[2] );  // sorialgi 출력
```

## 배열의 효용성
배열이 없다면 불편한 점이 많게 된다. 데이터를 담아야하는 변수도 배열에 넣어주려는 원소 수 만큼 있어야하며 응답을 여러개 주는 함수를 사용할 수 없기 때문에 그 만큼 함수 수도 늘어나게 될 것이다.
```
#멈버를 얻는 함수가 멤버 개수 만큼 증가
function get_member1(){
  return 'egoing';
}
console.log( get_member1() );

funjction get_member2(){
  return 'k8805';
}
console.log( get_member2() );

#배열을 사용하여 함수에서 배열를 응답으로 던짐
function get_member(){
  return ['egoing'. k8805'];
}

var members = get_member();
console.log( members[0] );
console.log( members[1] );
```

## 배열의 사용
배열이 반복문을 만나면 엄청난 시너지가 생긴다.
```
function get_members(){
  return ['egoing', 'k8805', 'sorialgi'];
}

var members = get_members();
console.log(members[0].toUpperCase())f;  // 각 원소를 대문자로 출력
console.log(members[1].toUpperCase()); 
console.log(members[2].toUpperCase());
```

위 코드도 틀린 것은 없지만 좋은 코드라고 할 수는 없다.
```
function get_members(){
  return ['egoing', 'k8805', 'sorialgi'];
}

var members = get_members();

for(var i = 0; i < members.length; i++){  // 배열 members 개수 만큼 반복 한다.(.length 속성으로 배열 개수를 알 수 있다.)
  console.log(members[i].toUpperCase());  // 인덱스에 변수를 넣어서 같은 코드지만 다른 데이터들을 반복 처리한다.
}
```

## 배열의 제어
>배열에 데이터를 추가/삭제/수정 같은 작업을 편리하게 할 수 있는 기능을 제공한다.
- 배열의 크기 : 변수.length
```
var arr = [1,2,3,4,5];
console.log( arr.length );
```
- 배열에 추가 : 변수.push(넣을 값)
```
var li = ['a', 'b', 'c', 'd', 'e'];
li.push('f');  // 배열 맨 뒤에 추가
console.log(li);  // a, b, c, d, e, f 출력
```
- 복수의 원소를 배열에 추가 : 변수.concat(배열)
```
var li = ['a', 'b', 'c', 'd', 'e'];
li = li.concat(['f', 'g']);  // 배열끝에 배열 추가
console.log(li);  // a, b, c, d, e, f, g 출력
```
- 배열의 시작점에 원소를 추가 : 변수.unshift(넣을 값)
```
var li = ['a', 'b', 'c', 'd', 'e'];
li.unshift('z');  // 배열 제일 앞에 추가
console.log(li);  // z, a, b, c, d, e 출력
```
- 배열의 특정구간을 추출하거나, 특정구간에 배열을 추가함 : 변수.splice(index, howmany, element1, ..., elementN)
```
var a = ['a', 'b', 'c'];
a.splice(1, 0, 'd');  // index 1번에 d 추가
console.log(a);  // a, d, b, c 출력

var b = ['a', 'b', 'c'];
b.splice(1, 1, 'x', 'y');  // index 1번에 1개의 원소를 삭제한 후 x, y 추가
console.log(b);  // a, x, y, c 출력
```
참고(생활코딩) - <https://opentutorials.org/course/50/110>

## 배열 제거, 정렬
- 배열에서 첫번째 원소 제거 : 변수.shift()
```
var li = ['a', 'b', 'c', 'd', 'e'];
li.shift();  // 맨 앞의 a를 응답 주며 배열에서 제거
console.log(li);  // b, c, d, e 출력
```
- 배열의 마지막 원소 제거 : 변수.pop()
```
var li = ['a', 'b', 'c', 'd', 'e'];
li.pop();  // 배열의 맨뒤 e를 응답 두며 배열에서 제거
console.log(li); // a, b, c, d 출력
```
- 배열 정렬 : 변수.sort()
```
var li = ['c', 'e', 'a', 'b', 'd'];  // 정렬 되지 않은 배열
li.sort();  // 알파벳 순서 정렬
console.log(li);  // a, b, c, d, e 출력
```
- 배열 역순 정렬 : 변수.reverse()
```
var li = ['c', 'e', 'a', 'b', 'd'];  // 정렬 되지 않은 배열
li.reverse();  // 역순 정렬
console.log(li);  // e, d, c, b, a 출력
```
- 임의의 방식으로 정렬 : 변수.sort(sortfunc)
```
function sortNumber(a,b){
    // 비교 대상인 a와 b가 인자로 전달된다.
    //alert('a :'+a+', b:'+b);
    // a에서 b를 뺀 결과가 음수면 a가 b보다 작고, 0이면 같다.
    // sort메소드는 return 값이 음수,양수,0인지에 따라서 순서를 정한다.
    return a-b;
}
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
alert(numbers.sort(sortNumber)); // array, [1,2,3,4,5,6,7,8,9,10,20]
```
참고(생활코딩) - <https://opentutorials.org/course/50/109>
