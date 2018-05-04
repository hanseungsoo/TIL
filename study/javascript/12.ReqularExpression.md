# Javascript - 정규표현식
> 문자열에서 특정 문자를 찾아내는 도구  
정규표현식 자체에 대한 공부는 <https://opentutorials.org/course/909/5142> 참고

## 정규표현식 생성
> 정규표현식을 생성하는 컴파일 과정이다.
- 정규표현식 리터럴 : '/'와 '/' 사이에 들어있는 패턴을 찾는다.
```
var pattern = /a/;
```
- 정규표현식 객체 생성자 : 정규표현식 객체의 생성자로 찾을 패턴을 넣어준다.
```
var pattern = new RegExp('a');
```

## RegExp 객체의 사용
> 생성된 정규표현식 객체를 이용하여 문자열에서 원하는 문자를 찾는다.
- 추출 : RegExp.exec(대상 문자열)
```
var pattern = /a/;  // pattern은 정규표현식 객체
pattern.exec('abcde');  // 'a' 출력
pattern.exec('bcde');  // null 출력
```
- 테스트 : ReqExp.test(대상 문자열)
```
var pattern = /a/;
pattern.test('abcde');  // true 리턴
pattern.test('bcde');  // false 리턴

## String과 정규표현식
- 대상문자열.match(패턴) : 문자열에서 추출
```
var pattern = /a/;
'abcdef'.match(pattern); // a 출력
```
- 대상문자열.replace(패턴, 바뀔문자) : 대상문자열에서 패턴으로 검색하여 치환
```
var pattern = /a/;
'abcdef'.replace(pattern, 'A');  // Abcdef 출력
```

## 옵션
> 정규표현식 패턴을 만들때 옵션을 넣을 수 있다.
- i옵션 : 대소문자를 구분하지 않는다.
```
var oi = /a/i;
'Abcde'.match(oi);  // A 출력
```
- g옵션 : 검색된 모든 결과를 리턴한다.
```
var xg = /a/;
'abcdea'.match(xg);  // a하나만 출력

var og = /a/g;
'abcdea'.match(og);  // a 두개 출력
```
옵션은 같이 사용할 수 있다.

## 캡처
> 패턴에 사용된 그룹을 기준으로 가져와 사용할 수 있는 기능
```
var pattern = /(\w+)\s(\w+)/;
var str = 'conding everybody';

var result = str.replace(pattern, '$2, $1');  // $2, $1은 각각 그룹을 의미
console.log(result);  // everybody, coding 출력
```

## 치환
var urlPattern = /\b(?:https?):\/\/[a-z0-9-+&@#\/%?=~_|!:,.;]*/gim;
var content = '생활코딩 : http://opentutorials.org/course/1 입니다. 네이버 : http://naver.com 입니다. ';
var result = content.replace(urlPattern, function(url){ // replace 뒤에 함수를 인자로 주면 패턴이 매칭되는 것을 찾을 때마다 함수를 호출 한다.
    return '<a href="'+url+'">'+url+'</a>';
});
console.log(result);

## 참고
정규표현식 빌더 - <https://regexr.com>
정규표현식을 시각화 - <https://regexper.com>
