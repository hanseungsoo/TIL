# Javascript - 객체
>객체의 여러 기능중 하나인 데이터를 담아내는 기능을 요번 시간에 공부하자!!  
배열은 데이터를 넣으면 숫자 인덱스가 차례로 할당되었다. 객체는 그 인덱스를 사용자가 설정할 수 있다 (ex. first, second 등..)

## 객체의 생성
```
# 방법 1
var grades = { 'egoing' : 10, 'k8805' : 6, 'sorialgi' : 80 };
# 방법 2
var grades = {};
grades['egoing'] = 10;
grades['k8805'] = 6;
grades['sorialgi'] = 80;
# 방법 3
var grades = {};
grades['egoing'] = 10;
grades['k8805'] = 6;
grades['sorialgi'] = 80;

방법1, 방법2, 방법3은 같다.
```
위와 같이 객체를 생성하는 것은 배열의 선언과 유사하다. 이 예제에서 egoing, k8805, sorialgi는 인덱스에 해당하는 키(key)이고 10, 6, 80 들은 해당 인덱스에 해당하는 값(value)들이다. 

## 객체에서 필요한 값을 꺼내기
```
var grades = { 'egoing' : 10, 'k8805' : 6, 'sorialgi' : 80 };
console.log(grades['sorialgi']);  // 숫자 80 출력
console.log(grades.k8805);  // 숫자 6 출력
console.log(grades['k88'+'05']);  // 숫자 6 출력 

console.log(grades.'k88'+'05')  // Syntax 에러
```
배열에 인덱스를 넣어서 인덱스에 해당하는 데이터를 꺼냈듯이 객체에 인덱스에 해당하는 key를 넣어줘서 데이터를 꺼낸다.

## 객체와 반복문
>객체에 저장된 데이터를 다루기 위해 반복문을 사용할 수 있다.
```
var grades = { 'egoing' : 10, 'k8805' : 6, 'sorialgi' : 80 };
for(key in grades){  객체에서 key를 하나씩 꺼낸다.
  console.log("key : " + key + " value : " + grades[key]);  // for문에서 가져온 key로 객체에서 값을 출력한다.
}
```
for-in문을 객체에 사용하게 되면 객체의 key를 하나씩 꺼내 사용하게 된다.

## 객체에 넣을 수 있는 것들
```
var grades = {
    'list': {'egoing': 10, 'k8805': 6, 'sorialgi': 80},
    'show' : function(){
        for(var name in this.list){
            console.log(name+':'+this.list[name]");  // 여기서 this는 이 함수가 속해 있는 객체를 가르킨다.(약속된 키워드)
        }
    }
};
grades['list'];  // grades 객체 내의 list를 key로 가지는 또다른 객체
grades['list']['egoing'];  // 숫자 10을 출력
grades['show']();  // 객체에 show를 key로 가지는 함수 호출
grades.show();
```

## 객체 지향 프로그래밍
> 하나의 그릇안에 데이터와 함수를 모아 사용하는 방식
```
var grades = {
    'list': {'egoing': 10, 'k8805': 6, 'sorialgi': 80},
    'show' : function(){
        for(var name in this.list){
            console.log(name+':'+this.list[name]);
        }
    }
};
grades.show();  // grades 객체의 함수를 사용하여 데이터를 꺼낸다.
```
