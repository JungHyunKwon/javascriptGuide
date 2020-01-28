# 자바스크립트 가이드 v1.0.0
이 문서는 일관성, 가독성, 유지 보수 용이성을 위한 참고 자료입니다.

## 기본

### strict 모드
파일, 태그, 자기호출함수 첫 줄에 strict 모드를 사용합니다.

````javascript
'use strict';
````

### 작성자 주석
````javascript
/**
 * @author 작성자
 * @description 설명
 * @since 연-월-일
 * @version 버전
 */
````
#### 버전
추가, 변경, 삭제를 했을 때 버전을 올립니다.

* 0.0.1 ~ 0.5.0 : 알파
* 0.5.1 ~ 0.9.9 : 베타
* 1.0.0 ~ : 서비스

##### 버전상승 방법

* 큰 틀일 때 1.0.0 올립니다.
* 함수 단위일 때 0.1.0 올립니다.
* 짧은 구문일 때 0.0.1 올립니다.

### 들여쓰기
4칸

````javascript
  //Bad
  var helloWorld = 'helloWorld';

    //Good
    var helloWorld = 'helloWorld';
````

### 부호

#### 따옴표
작은따옴표로 통일하며 작은따옴표 안에 큰따옴표는 상관없습니다.

````javascript
//Bad
var helloWorld = "helloWorld";


//Good
var helloWorld = 'helloWorld';
````

#### 중괄호
소괄호 마침[ ) ]이 끝나고 시작되는 중괄호 시작[ { ] 되기 전에 한 칸 띄웁니다.

````javascript
//example1

//Bad
var helloWorld = 'helloWorld';

if(helloWorld){
    //내용
}

//Good
var helloWorld = 'helloWorld';

if(helloWorld) {
    //내용
}

//example2

//Bad
var helloWorld = 'helloWorld',
    helloWorldLength = helloWorld.length;

for(var i = 0; i < helloWorldLength; i++){
    //내용
}

//Good
var helloWorld = 'helloWorld',
    helloWorldLength = helloWorld.length;

for(var i = 0; i < helloWorldLength; i++) {
    //내용
}
````

#### 소괄호
소괄호 시작[ ( ] 이전에 공백은 사용하지 않습니다.

````javascript
//example1

//Bad
var helloWorld = 'helloWorld';

if (helloWorld) {
    //내용
}

//Good
var helloWorld = 'helloWorld';

if(helloWorld) {
    //내용
}

//example2

//Bad
var helloWorld = 'helloWorld',
    helloWorldLength = helloWorld.length;

for (var i = 0; i < helloWorldLength; i++) {
    //내용
}

//Good
var helloWorld = 'helloWorld',
    helloWorldLength = helloWorld.length;

for(var i = 0; i < helloWorldLength; i++) {
    //내용
}
````

#### 물음표
물음표에 앞뒤 공백을 넣습니다.

````javascript
//Bad
var helloWorld = 'helloWorld';

(helloWorld === 'helloWorld')?true : false;

//Good
var helloWorld = 'helloWorld';

(helloWorld === 'helloWorld') ? true : false;
````

#### 콜론
콜론에 앞뒤 공백을 넣습니다.

````javascript
//example1

//Bad
var hello = {
    world:'world'
};

//Good
var hello = {
    world : 'world'
};

//example2

//Bad
var helloWorld = 'helloWorld';

(helloWorld === 'helloWorld') ? true:false;

//Good
var helloWorld = 'helloWorld';

(helloWorld === 'helloWorld') ? true : false;
````

#### 세미콜론

명령문 종료 시 반드시 세미콜론을 기입합니다.
````javascript
//Bad
var helloWorld = 'helloWorld'

//Good
var helloWorld = 'helloWorld';
````

의미 없는 세미콜론 및 문자를 사용하지 않습니다.
````javascript
//Bad
;function helloWorld() {
    //내용
}

//Bad
+function helloWorld() {
    //내용
}

//Bad
!function helloWorld() {
    //내용
}

//Good
function helloWorld() {
    //내용
}
````

변수 선언을 제외한 중괄호 마침[ } ] 뒤에 세미콜론을 넣지 않습니다.
````javascript
//Bad
function helloWorld() {
    //내용
};

//Good
function helloWorld() {
    //내용
}

//Good
var helloWorld = function() {
    //내용
};
````

#### 연산자
연산자를 쓸 때 앞뒤 공백을 사용합니다.

````javascript
//Bad
var helloWorld=1;

//Good
var helloWorld = 1;
````

##### 증감 연산자
증감 연산자는 앞뒤 공백을 사용하지 않습니다.

````javascript
//Bad
var helloWorld = 1;

helloWorld ++;

//Good
var helloWorld = 1;

helloWorld++;
````

##### 복합 대입 연산자
````javascript
//Bad
var helloWorld = 1;

helloWorld = helloWorld + 1;

//Good
var helloWorld = 1;

helloWorld += helloWorld;
````

##### 비교 연산자
삼 항 연산자를 기본으로 하며 상황에 따라서 다르게 써도 됩니다.

````javascript
//Bad
var helloWorld = 'helloWorld';

if(helloWorld == 'helloWorld') {
    //내용
}

//Good
var helloWorld = 'helloWorld';

if(helloWorld === 'helloWorld') {
    //내용
}
````

특정 값을 골라내야만 할 때 빼고는 이 구문을 사용합니다.
````javascript
//example1

//Bad
var helloWorld = true;

if(helloWorld === true) {
    //내용
}

//Good
var helloWorld = true;

if(helloWorld) {
    //내용
}

//example2

//Bad
var helloWorld = false;

if(helloWorld === false) {
    //내용
}

//Good
var helloWorld = false;

if(!helloWorld) {
    //내용
}
````

아래 값은 false에 해당하는 값이며 나머지 값은 true입니다.

* null
* NaN
* 0
* 공백
* undefined

### 개행
가독성을 위해 개행을 합니다.

````javascript
//example1

//Bad
var hello1 = 1, hello2 = 1, world1 = 1, world2 = 1;

//Good
var hello1 = 1,
    hello2 = 1,

    world1 = 1,
    world2 = 1;

//example2

//Bad
var hello1 = 1,
    hello2 = 1,
    world1 = 1,
    world2 = 1;

hello1++;
hello2++;
world2++;
world2++;

//Good
var hello1 = 1,
    hello2 = 1,

    world1 = 1,
    world2 = 1;

hello1++;
hello2++;

world2++;
world2++;

//example3

//Bad
var helloWorld = ['helloWorld1', 'helloWorld2', 'helloWorld3', 'helloWorld4', 'helloWorld5', 'helloWorld6', 'helloWorld7', 'helloWorld8', 'helloWorld9', 'helloWorld10'];

//Good
var helloWorld = [
    'helloWorld1',
    'helloWorld2',
    'helloWorld3',
    'helloWorld4',
    'helloWorld5',
    'helloWorld6',
    'helloWorld7',
    'helloWorld8',
    'helloWorld9',
    'helloWorld10'
];

//Good
var helloWorld = ['helloWorld1',
                  'helloWorld2',
                  'helloWorld3',
                  'helloWorld4',
                  'helloWorld5',
                  'helloWorld6',
                  'helloWorld7',
                  'helloWorld8',
                  'helloWorld9',
                  'helloWorld10'];

//example4

//Bad
var helloWorld = {hello1 : 'world1', hello2 : 'world2', hello3 : 'world3', hello4 : 'world4', hello5 : 'world5', hello6 : 'world6', hello7 : 'world7', hello8 : 'world8', hello9 : 'world9', hello10 : 'world10'};

//Good
var helloWorld = {
    hello1 : 'world1',
    hello2 : 'world2',
    hello3 : 'world3',
    hello4 : 'world4',
    hello5 : 'world5',
    hello6 : 'world6',
    hello7 : 'world7',
    hello8 : 'world8',
    hello9 : 'world9',
    hello10 : 'world10'
};

//Good
var helloWorld = {hello1 : 'world1',
                  hello2 : 'world2',
                  hello3 : 'world3',
                  hello4 : 'world4',
                  hello5 : 'world5',
                  hello6 : 'world6',
                  hello7 : 'world7',
                  hello8 : 'world8',
                  hello9 : 'world9',
                  hello10 : 'world10'};
````

누가 봐도 보기 좋게 개행하면 어떻게 개행해도 좋습니다.

#### 콤마
콤마 다음은 한 칸 띄웁니다. 개행했을 때 하지 않습니다.

````javascript
//Bad
function helloWorld(nm,say) {
    return nm + ' : ' + say;
}

//Good
function helloWorld(nm, say) {
    return nm + ' : ' + say;
}
````

### 이름

#### 변수
전역 변수의 오염은 피하며 카멜 표기법을 지향합니다.

````javascript
//Bad
var helloworld = 'helloWorld';

//Good
var helloWorld = 'helloWorld';
````

#### 상수(값이 변할 수 없음)
* 상수 표기는 전체 대문자 + 스네이크 표기법으로 작성합니다.

````javascript
//Bad
var helloWorld = 'helloWorld';

//Good
var HELLO_WORLD = 'helloWorld';
````

객체, 배열, 객체에 프로퍼티 이름은 상수를 사용하지 않습니다.
````javascript
//example1

//Bad
var HELLO = {};

//Good
var hello = {};

//Good
var _hello = {};

//example2

//Bad
var HELLO = [];

//Good
var hello = [];

//Good
var _hello = [];

//example3

//Bad
var hello = {
    WORLD : 'world'
};

//Good
var hello = {
    _world : 'world'
};

//Good
var hello = {
    world : 'world'
};
````

값이 변하지 않는다고 무조건 상수로 두지 않습니다. 이 값은 건드리면 안 된다. 하는 것을 상수로 표현합니다.
````javascript
//Bad
 var HELLO_WORLD = 'helloWorld',
     HELLO_WORLD_LENGTH = 10;

//Good
 var helloWorld = 'helloWorld',
     HELLO_WORLD_LENGTH = 10;
````

#### 은닉(값이 숨겨져 할당된 값을 수정할 수 없는 위치에 있음)
할당된 값을 변경하지 말자는 약속이며 맨 앞에 언더 스코어를 붙여 작성합니다.

````javascript
//Bad
var helloWorld = 'hellowWorld';

//Good
var _helloWorld = 'helloWorld';
````

상수와 은닉은 섞어 사용하지 않습니다.
````javascript
//Bad
var _HELLO_WORLD = 'helloWorld';

//Good
var _helloWorld = 'helloWorld';

//Good
var HELLO_WORLD = 'helloWorld';
````

#### 생성자
파스칼 표기법으로 작성합니다.

````javascript
//Bad
var newHelloWorld = new helloWorld();

function helloworld() {
    this.helloWorld = 'helloWorld';
}

//Good
var newHelloWorld = new HelloWorld();

function Helloworld() {
    this.helloWorld = 'helloWorld';
}
````
#### 축약
이름이 너무 길어 축약이 필요한 경우는 음절로 축약하거나 주석으로 축약어를 제공하거나 누구나 알아볼 수 있어야 됩니다.
````javascript
//before
var functionType = typeof function() {};

//after
var fnType = typeof function() {};
````

#### 용어

이름 | 축악 후 이름 | 의미
| :------- | :------- | :-- |
name | nm | 이름
function | fn | 함수
temp | tmp | 임시
global | g | 전역
local | l | 지역
index | idx | 색인
count | cnt | 셈
length | len | 갯수
array | arr | 배열
object | obj | 객체
value | val | 값
button | btn | 버튼
mobile | m | 모바일
arguments | args | 인자
message | msg | 메세지
string | str | 문자
number | num | 숫자
boolean | bool | 부울
error | err | 오류

루프 변수는 i부터 시작합니다.

#### 규칙
* 명사 + 명사
* 형용사 + 명사
* 명사 + 전치사 + 명사
* 명사

객체 프로퍼티명도 동일합니다.

#### 금지 단어
<https://www.w3schools.com/js/js_reserved.asp>를 피해서 작성해야 합니다.

#### 파일
아래 순서대로 이름을 온점[ . ] 단위로 조합하여 파일 이름을 작명합니다.

1. 컴포넌트명
2. 모듈명, 메서드명, 함수명
3. min

### 생략

중괄호[ {} ]를 생략하지 않습니다.
````javascript
//example1

//Bad
var helloWorld = 'helloWorld';

if(helloWorld)
    helloWorld = 'helloWorld';

//Good
var helloWorld = 'helloWorld';

if(helloWorld) {
    helloWorld = 'helloWorld';
}

//example2

//Bad
var helloWorld = 5;

for(var i = 0; i < helloWorld; i++) //내용

//Good
var helloWorld = 5;

for(var i = 0; i < helloWorld; i++) {
    //내용
}
````

한 줄 if 문에서 소괄호[ () ]를 생략하지 않습니다.
````javascript
//Bad
var helloWorld = 'helloWorld';

helloWorld === 'helloWorld' ? true : false;

//Good
var helloWorld = 'helloWorld';

(helloWorld === 'helloWorld') ? true : false;
````

## 변수선언

여러 번 선언하지 않는다. 상황에 따라서 분리가 필요할 때 분리할 수 있습니다.
````javascript
//Bad
var hello = 'hello';
var world = 'world';

//Good
var hello = 'hello',
    world = 'world';
````

선언 키워드 없이 변수 선언을 해서는 안됩니다.
````javascript
//Bad
helloWorld = 'helloWorld';

//Good
var helloWorld = 'helloWorld';
````

undefined를 유도한 값이 아니라면 초기화를 해주며 예외가 있을 경우 예외에 맞게 작성하면 됩니다.
````javascript
//Bad
var hello = 'hello',
    world;

world = 'world';

//Good
var hello = 'hello',
    world = 'world';
````

필요한 구문에서 변수 할당하며 중복된 변수명은 상단에 선언합니다.
````javascript
//example1

//Bad
var hello = 'hello',
    world = undefined;

if(hello) {
    world = 'world';
}

//Good
var hello = 'hello';

if(hello) {
    var world = 'world';
}

//example2

//Bad
var hello = 'hello';

if(hello) {
    var world = 'world';
}else{
    var world = undefined;
}

//Good
var hello = 'hello',
    world;

if(hello) {
    world = 'world';
}

//example3

//Bad
var helloWorld = 'helloWorld';

for(var i = 0, helloWorldLength = helloWorld.length; i < helloWorldLength; i++) {
    //내용
}

for(var i = 0, helloWorldLength = helloWorld.length; i < helloWorldLength; i++) {
    //내용
}

for(var i = 0, helloWorldLength = helloWorld.length; i < helloWorldLength; i++) {
    //내용
}

//Bad
var helloWorld = 'helloWorld',
    helloWorldLength = helloWorld.length;

for(var i = 0; i < helloWorldLength; i++) {
    //내용
}

for(var i = 0; i < helloWorldLength; i++) {
    //내용
}

for(var i = 0; i < helloWorldLength; i++) {
    //내용
}

//Good
var helloWorld = 'helloWorld',
    helloWorldLength = helloWorld.length,
    i;

for(i = 0; i < helloWorldLength; i++) {
    //내용
}

for(i = 0; i < helloWorldLength; i++) {
    //내용
}

for(i = 0; i < helloWorldLength; i++) {
    //내용
}
````

같은 값을 선언할 때 구문입니다.
````javascript
//Bad
var hello = world = 'helloWorld';

//Good
var hello = 'helloWorld',
    world = hello;
````

값에 따라 바뀌는 변수일 때 구문입니다.
````javascript
//example1

//Bad
function helloWorld(say) {
    var result = say;

    if(!result) {
        result = 'helloWorld';
    }

    return result;
}

//Good
function helloWorld(say) {
    return say || 'helloWorld';
}

//example2

//Bad
function helloWorld(say) {
    var result = say;

    if(result) {
        result = undefined;
    }

    return result;
}

//Good
function helloWorld(say) {
    return say && undefined;
}
````

\#.length를 여러 번 사용할 때 변수에 담아 사용합니다.
````javascript
//Bad
var helloWorld = 'helloWorld';

for(var i = 0; i < helloWorld.length; i++) {
    //내용
}

//Good
var helloWorld = 'helloWorld',
    helloWorldLength = helloWorld.length;

for(var i = 0; i < helloWorldLength; i++) {
    //내용
}

//Good
var helloWorld = 'helloWorld';

for(var i = 0, helloWorldLength = helloWorld.length; i < helloWorldLength; i++) {
    //내용
}
````

## 객체

리터럴 구문을 사용합니다.
````javascript
//Bad
var helloWorld = new Object();

//Bad
var helloWorld = Object();

//Good
var helloWorld = {};
````

프로퍼티의 맨 마지막 콤마는 적지 않습니다.
````javascript
//Bad
var hello = {
    world : 'world',
};

//Good
var hello = {
    world : 'world'
};
````

속성 이름을 JSON 속성 이름처럼 작성하지 않습니다.
````javascript
//Bad
var hello = {
    'world' : 'world'
};

//Good
var hello = {
    world : 'world'
};
````

## 배열

리터럴 구문을 사용합니다.
````javascript
//Bad
var helloWorld = new Array();

//Bad
var helloWorld = Array();

//Good
var helloWorld = [];
````

특정 위치에 값을 넣어야 할 때 빼고는 항목에 대입하지 않고 push를 사용합니다.
````javascript
//Bad
var helloWorld = [];

helloWorld[helloWorld.length] = 'helloWorld';

//Good
var helloWorld = [];

helloWorld.push('helloWorld');
````

배열을 복사할 때는 이 구문을 사용합니다.
````javascript
//Bad
var helloWorld = ['helloWorld1', 'helloWorld2', 'helloWorld3'],
    helloWorldLength = helloWorld.length,
    newHelloWorld = [];

for(var i = 0; i < helloWorldLength; i++) {
    newHelloWorld.push(helloWorld[i]);
}

//Good
var helloWorld = ['helloWorld1', 'helloWorld2', 'helloWorld3'],
    helloWorldLength = helloWorld.length,
    newHelloWorld = helloWorld.slice();
````

## 문자
````javascript
//Bad
var helloWorld = new String('helloWorld');

//Bad
var helloWorld = String('helloWorld');

//Good
var helloWorld = 'helloWorld';
````

### parseInt
문자형에서 숫자형으로 변환할 때 특정 값을 유도할 때 빼고는 parseInt 메서드를 사용하며 10진법을 명시합니다.

````javascript
//Bad
var helloWorld = new Number('1');

//Bad
var helloWorld = Number('1');

//Bad
var helloWorld = parseInt('1');

//Good
var helloWorld = parseInt('1', 10);
````

형변환이 필요할때 아래구문을 이용합니다.
````javascript
//Bad
var helloWorld = 1.toString();

//Bad
var helloWorld = String(1);

//Bad
var helloWorld = new String(1);

//Good
var helloWorld = 1 + '';
````

## 숫자
형 변환이 필요할 때 parseInt 메서드를 기본으로 사용하며 예외 빼고는 아래 구문을 이용합니다.

````javascript
//Bad
var helloWorld = new Number(1);

//Bad
var helloWorld = Number(1);

//Good
var helloWorld = 1;
````

## 불리언
형 변환이 필요할 때 빼고는 아래 구문을 이용합니다.

````javascript
//Bad
var helloWorld = new Boolean(true);

//Bad
var helloWorld = Boolean(true);

//Good
var helloWorld = true;
````

## 함수
<http://usejsdoc.org/>에 맞춰 작성합니다.

선언함수를 사용합니다.
````javascript
//Bad
var helloWorld = function() {
    //내용
};

//Good
function helloWorld() {
    //내용
}
````

즉시 실행 함수는 이 구문을 사용합니다.
````javascript
(function() {
    //내용
})();

(function() {
   //내용
}());
````

함수 호출을 줄입시다.
````javascript
//Bad
document.getElementsByTagName('body')[0].style.color = '#fff';
document.getElementsByTagName('body')[0].style.backgroundColor = '#000';

//Good
var body = document.getElementsByTagName('body')[0];

body.style.color = '#fff';
body.style.backgroundColor = '#000';
````

한 번만 반환하며 특별한 경우가 아닌 경우 변수명은 result로 통일합니다.
````javascript
//Bad
function helloWorld(say) {
    if(say === 'hello') {
        return true;
    }else if(say === 'world') {
        return false;
    }
}

//Bad
function helloWorld(say) {
    var result;

    if(say === 'hello') {
        result = true;

        return result;
    }else if(say === 'world') {
        result = false;

        return result;
    }
}

//Good
function helloWorld(say) {
    var result;

    if(say === 'hello') {
        result = true;
    }else if(say === 'world') {
        result = false;
    }

    return result;
}
````

오류를 유발할 수 있는 구문은 try catch finally를 이용하며 try 중괄호 마침[ } ] 뒤에 catch 또는 finally가 반드시 붙어야 됩니다.
````javascript
//Bad
function helloWorld(say) {
    var result = eval(hello + say),
        hello = 'hello';

    return result;
}

//Good
function helloWorld(say) {
    var result;

    try {
        result = eval(hello + say);
    }catch(e) {
        result = say;
    }finally{
        console.log('끝났다.');
    }
    
    var hello = 'hello';

    return result;
}
````

### 규칙
* 동사 + 명사
* 동사 + 형용사 + 명사
* 동사 + 명사 + 전치사 + 명사
* 명사

## 제이쿼리

제이쿼리 호출 순서입니다.
````javascript
console.log(1);
    
$(function() {
    console.log(2);
    
    //외부자원(img, iframe, script, css, js...)
    $('img').on('load', function(event) {
        console.log(4);
    });
});

$(document).on('ready', function(event) {
    console.log(3);
});
    
$(window).on('load', function(event) {
    console.log(5);
});
````

제이쿼리 요소 변수는 $로 시작합니다.
````javascript
//Bad
var body = $('body');

//Good
var $body = $('body');
````

제이쿼리 작성할 때 이 구문을 사용합니다.
````javascript
(function($) {
    //내용
})(jQuery);
````

변수에 정의하여 재사용합니다.
````javascript
//Bad

//1.js
$(function() {
    var $body = $('body');

    $body.css('background-color', '#000');
});

//2.js
$(function() {
    $body.css('color', '#fff'); //$body를 찾지못함.
});

//Good

//1.js
$(function() {
    window.element = {
        $body : $('body')
    };

    element.$body.css('background-color', '#000');
});

//2.js
$(function() {
    element.$body.css('color', '#fff');
});
````

다수의 호출을 피하고 묶을 수 있는 메서드는 묶어 사용합니다.
````javascript
//example1

//Bad
$('body').addClass('hello');
$('body').addClass('world');

//Bad
var $body = $('body');

$body.addClass('hello');
$body.addClass('world');

//Bad
var $body = $('body');

$body.addClass('hello').addClass('world');

//Good
var $body = $('body');

$body.addClass('hello world');

//example2

//Bad
var $body = $('body');

$body.css('color', '#fff').css('background-color', '#000');

//Good
var $body = $('body');

$body.css({
    color : '#fff',
    backgroundColor : '#000'
});
````

이벤트에 네임스페이스를 부여하여 사용합니다.
````javascript
//Bad
$('body').on('click', function(event) {
    //내용
});

//Good
$('body').on('click.common', function(event) {
    //내용
});
````

이벤트는 on 메서드를 사용합니다.
````javascript
//Bad
$('body').click(function(event) {
    //내용
});

//Good
$('body').on('click', function(event) {
    //내용
});
````

이벤트 콜백 함수에 매개변수 event를 기입합니다.
````javascript
//Bad
$('body').on('click', function() {
    //내용
});

//Good
$('body').on('click', function(event) {
    //내용
});
````

필요한 경우 이외에 trigger 대신 triggerHandler를 사용합니다.
````javascript
//Bad
var $body = $('body');

$body.on('click', function() {
    //내용
});

$body.trigger('click');

//Good
var $body = $('body');

$body.on('click', function() {
    //내용
});

$body.triggerHandler('click');
````

필요한 경우 이외에 전체 이벤트를 부르지 말고 특정 이벤트만 불러 사용합니다.
````javascript
//Bad
var $body = $('body');

$body.on('click.common', function() {
    console.log(1);
});

$body.on('click.main', function() {
    console.log(2);
});

$body.triggerHandler('click');

//Good
var $body = $('body');

$body.on('click.common', function() {
    console.log(1);
});

$body.on('click.main', function() {
    console.log(2);
});

$body.triggerHandler('click.common');
````

## 기준
ecma-262 3rd edition, december 1999