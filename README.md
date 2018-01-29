# 자바스크립트 가이드 v1.0
이 문서는 일관성, 가독성, 유지보수 용이성을 위한 참고자료입니다.

## 기본

### strict 모드
js파일 또는 스크립트 태그 첫줄에 strict 모드를 사용합니다.

````javascript
'use strict';
````

### 작성자 주석
````javascript
/**
 * @author 작성자
 * @since 연-월-일
 * @version 버전
 */
````

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
작은따옴표로 통일하며 작은따옴표안에 큰따옴표는 상관없습니다.

````javascript
//Bad
var helloWorld = "helloWorld";


//Good
var helloWorld = 'helloWorld';
````

#### 중괄호
소괄호 마침[ ) ]이 끝나고 시작되는 중괄호 시작[ { ]되기전에 한칸 띄웁니다.

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
소괄호 시작[ ( ]이전에 공백은 사용하지 않습니다.

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

명령문 종료시 반드시 세미콜론을 기입합니다.
````javascript
//Bad
var helloWorld = 'helloWorld'

//Good
var helloWorld = 'helloWorld';
````

의미없는 세미콜론 및 문자를 사용하지 않습니다.
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

변수선언을 제외한 중괄호 마침[ } ]뒤에 세미콜론을 넣지 않습니다.
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
연산자를 쓸때 앞뒤 공백을 사용합니다.

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
삼항연산자를 기본으로하며 상황에따라서 다르게 써도 됩니다.

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

특정값을 골라내야만 할때 빼고는 이 구문을 사용합니다.
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

아래값은 false에 해당하는 값이며 나머지값은 true입니다.

* null
* NaN
* 0
* 공백
* undefined

### 개행
가독성을위해 개행을 합니다.

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

누가봐도 보기좋게 개행하면 어떻게 개행하던 상관없습니다.

#### 콤마
콤마다음은 한칸 띄웁니다. 개행했을때는 하지않습니다.

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
기본은 카멜 표기법입니다.

````javascript
//Bad
var helloworld = 'helloWorld';

//Good
var helloWorld = 'helloWorld';
````

#### 상수(값이 변할 수 없음)
* 상수표기는 전체 대문자 + 스네이크 표기법으로 작성합니다.

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

값이 변하지 않는다고 무조건 상수로 두지 않습니다. 이 값은 건드리면 안된다. 하는것을 상수로 표현합니다.
````javascript
//Bad
 var HELLO_WORLD = 'helloWorld',
     HELLO_WORLD_LENGTH = 10;

//Good
 var helloWorld = 'helloWorld',
     HELLO_WORLD_LENGTH = 10;
````

#### 은닉(값이 숨겨져 할당된 값을 수정할 수 없는 위치에 있음)
할당된 값을 변경하지 말자는 약속이며 맨앞에 언더스코어를 붙여 작성합니다.

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
이름이 너무길어 축약이 필요한 경우는 음절로 축약하거나 주석으로 축약어를 제공하거나 누구나 알아볼 수 있어야 됩니다. 
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
result | rst | 결과
global | g | 전역
local | l | 지역
index | idx | 인덱스
count | cnt | 카운트
length | len | 갯수
array | arr | 배열
object | obj | 객체
value | val | 값
current | crt | 현재
active | atv | 활성화
actived | atvd | 활성화된
prev | prv | 이전
next | nxt | 다.음
is | | ~~인가?
has | | 가지고 있는지
i ~ z | | 루프변수
all | a | 모든
button | btn | 버튼
mobile | m | 모바일
arguments | args | 인자
message | msg | 메세지

루프변수는 i부터 시작합니다.

#### 규칙
* 명사 + 명사
* 형용사 + 명사
* 명사 + 전치사 + 명사
* 명사

객체 프로퍼티명도 동일합니다.

#### 금지단어
<https://www.w3schools.com/js/js_reserved.asp>를 피해서 작성해야 합니다.

#### 파일
아래 순서대로 이름을 온점[ . ]단위로 조합하여 파일이름을 작명합니다.

1. 컴포넌트명
2. 모듈명 또는 메소드명
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

한줄 if문에서 소괄호[ () ]를 생략하지 않습니다.
````javascript
//Bad
var helloWorld = 'helloWorld';

helloWorld === 'helloWorld' ? true : false;

//Good
var helloWorld = 'helloWorld';

(helloWorld === 'helloWorld') ? true : false;
````

## 변수선언

여러번 선언하지 않는다. 상황에 따라서 분리가 필요할때 분리할 수 있습니다.
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

undefined를 유도한 값이 아니라면 초기화를 해주며 예외가 있을경우 예외에 맞게 작성하면 됩니다.
````javascript
//Bad
var hello = 'hello',
    world;

world = 'world';

//Good
var hello = 'hello',
    world = 'world';
````

필요한 구문에서 변수할당하며 중복된 변수명은 상단에 선언합니다.
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

같은 값을 선언할때 구문 입니다.
````javascript
//Bad
var hello = world = 'helloWorld';

//Good
var hello = 'helloWorld',
    world = hello;
````

값에 따라 바뀌는 변수일때 구문입니다.
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
    var result = say || 'helloWorld';

    return result;
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
    var result = say && undefined;

    return result;
}
````

\#.length를 여러번 사용할때 변수에 담아 사용합니다.
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

프로퍼티의 맨마지막 콤마는 적지않습니다.
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

프로퍼티명을 JSON 프로퍼티명처럼 작성하지 않습니다.
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

객체를 복사할때 이 함수를 사용한다.
````javascript
//copyObject.js

/**
 * @name 객체복사
 * @author JungHyunKwon
 * @since 2018-01-28
 * @version 1.0
 * @param {*} object
 * @return {*}
 */
function copyObject(object) {
    var result = {};

    if(object instanceof Object) {
        for(var i in object) {
            if(object.hasOwnProperty(i)) {
                result[i] = copyObject(object[i]);
            }
        }
    }else{
        result = object;
    }

    return result;
}
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

특정위치에 값을 넣어야할때 빼고는 항목에 대입하지않고 push메소드를 사용합니다.
````javascript
//Bad
var helloWorld = [];

helloWorld[helloWorld.length] = 'helloWorld';

//Good
var helloWorld = [];

helloWorld.push('helloWorld');
````

배열을 복사할때는 이 구문을 사용합니다.
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

### parseInt 메소드
문자형에서 숫자형으로 변환할때 특정값을 유도할때 빼고는 parseInt메소드를 사용하며 10진법을 명시합니다.

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
형변환이 필요할때 parseInt메소드를 기본으로 사용하며 예외빼고는 아래 구문을 이용합니다.

````javascript
//Bad
var helloWorld = new Number(1);

//Bad
var helloWorld = Number(1);

//Good
var helloWorld = 1;
````

## 불린
형변환이 필요할때 빼고는 아래 구문을 이용합니다.

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

즉시실행함수는 이 구문을 사용합니다.
````javascript
(function() {
    //내용
})();

(function() {
   //내용
}());
````

함수호출을 줄입시다.
````javascript
//Bad
document.getElementsByTagName('body')[0].style.color = '#fff';
document.getElementsByTagName('body')[0].style.backgroundColor = '#000';

//Good
var body = document.getElementsByTagName('body')[0];

body.style.color = '#fff';
body.style.backgroundColor = '#000';
````

한번만 반환하며 특별한 경우가 아닌경우 변수명은 result로 통일합니다.
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

오류를 유발할 수 있는 구문은 try catch finally를 이용하며 try 중괄호 마침[ } ]뒤에 catch또는 finally가 반드시 붙어야됩니다.
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

try catch안에서의 전역함수는 익명함수로 작성합니다.
````javascript
//Bad
try {
    function helloWorld(say) {
        return say;
    }
}catch(e) {
    console.error(e);
}

//Bad
try {
    this.helloWorld = function(say) {
        return say;
    };
}catch(e) {
    console.error(e);
}

//Good
try {
    window.helloWorld = function(say) {
        return say;
    };
}catch(e) {
    console.error(e);
}
````

에뮬레이션이 아닌 실제 인터넷익스플로러9이하에서 콘솔오류를 막으려면 아래 함수를 사용합니다.
````html
<!--[if lt IE 10]><script src="consoleFix.js"></script><![endif]-->
````

````javascript
//consoleFix.js

/**
 * @name 콘솔오류방지
 * @author JungHyunKwon
 * @description 대체콘솔은 console.comment입니다.
 * @version 1.0
 * @since 2018-01-28
 */
if(!window.console instanceof Object) {
    window.console = {
        method : [
        'assert',
            'clear',
            'count',
            'debug',
            'dir',
            'dirxml',
            'error',
            'exception',
            'group',
            'groupCollapsed',
            'groupEnd',
            'info',
            'log',
            'markTimeline',
            'profile',
            'profileEnd',
            'table',
            'time',
            'timeEnd',
            'timeStamp',
            'trace',
            'warn'
    ],
        comment : []
    };

    for(var i = 0, consoleMethodLength = window.console.method.length; i < consoleMethodLength; i++) {
        if(typeof window.console[window.console.method[i]] !== 'function') {
            window.console[window.console.method[i]] = function() {
                var result = [],
                    argumentsLength = arguments.length;

                if(argumentsLength > 1) {
                    for(var i = 0; i < argumentsLength; i++) {
                        result.push(arguments[i]);
                    }
                }else if(argumentsLength === 1) {
                    result = arguments[0];
                }


                if(argumentsLength) {
                    this.comment.push(result);
                }

                return result;
            };
        }
    }
}
````

자세한 형태를 파악하고 싶다면 아래함수를 사용합니다.
````javascript
//getTypeof.js

/**
 * @name 형태얻기
 * @author JungHyunKwon
 * @since 2017-12-18
 * @version 1.0
 * @param {*} value
 * @return {string}
 */
function getTypeof(value) {
    var result = 'none';

    if(arguments.length) {
        result = Object.prototype.toString.call(value).toLowerCase().replace('[object ', '').replace(']', '');

        if(value === undefined) {
            result = 'undefined';
        }else if(result === 'number' && isNaN(value)) {
            result = 'NaN';
        }else if(result === 'number' && !isFinite(value)) {
            result = 'Infinity';
        }else if(result.substr(-8) === 'document') {
            result = 'document';
        }else if(result.substr(-7) === 'element') {
            result = 'element';
        }else if(typeof window.jQuery === 'function' && value instanceof window.jQuery) {
            var iCount = 0;

            for(var i in value) {
                var iType = getTypeof(value[i]);

                if((iType === 'window' || iType === 'document' || iType === 'element') && !isNaN(Number(i))) {
                    iCount++;
                }
            }

            if(value.length && value.length === iCount) {
                result = 'jQueryElement';
            }else{
                result = 'jQueryObject';
            }
        }else if(result === 'date' && isNaN(new Date(value))) {
            result = 'Invalid Date';
        }else if(result === 'function' && /^class\s/.test(value.toString())) {
            result = 'class';
        }
    }

    return result;
}
````

### 규칙
* 동사 + 명사
* 동사 + 형용사 + 명사
* 동사 + 명사 + 전치사 + 명사
* 명사

## 제이쿼리

제이쿼리 호출순서입니다.
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

제이쿼리 엘리먼트 변수는 $로 시작합니다.
````javascript
//Bad
var body = $('body');

//Good
var $body = $('body');
````

제이쿼리 작성할때 이 구문을 사용합니다.
````javascript
try {
    if(typeof window.jQuery === 'function') {
        (function($) {
            //내용
        })(jQuery);
    }else{
        throw '제이쿼리가 없습니다.';
    }
}catch(e) {
    console.error(e);
}
````

제이쿼리 엘리먼트는 $.tag에 정의하여 재사용합니다.
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
    $.tag = {
        body : $('body')
    };

    $.tag.body.css('background-color', '#000');
});

//2.js
$(function() {
    $.tag.body.css('color', '#fff');
});
````

다수의 호출을 피하고 묶을 수 있는 메소드는 묶어 사용합니다.
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

이벤트는 on메소드를 사용합니다.
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

필요한 경우 이외에 trigger대신 triggerHandler를 사용합니다.
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

필요한 경우 이외에 전체 이벤트를 부르지말고 특정 이벤트만 불러 사용합니다.
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