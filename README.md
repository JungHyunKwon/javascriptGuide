# 자바스크립트 가이드
이 문서는 일관성, 가독성, 유지보수 용이성을 위한 참고자료입니다.

## 기본

### strict 모드
js파일 또는 스크립트 태그 첫줄에 'use strict'를 반드시 적습니다.

### 들여쓰기
4칸

````
  //Bad
  var helloWorld = 'helloWorld';

    //Good
    var helloWorld = 'helloWorld';
````

### 부호

#### 따옴표
작은따옴표로 통일합니다.

````
    //Bad
    var helloWorld = "helloWorld";


    //Good
    var helloWorld = 'helloWorld';
````

#### 중괄호
소괄호 마침[)]이 끝나고 시작되는 중괄호 시작[{]되기전에 한칸 띄웁니다.

````
    //example1
    
    //Bad
    var helloWorld = 'helloWorld';

    if(helloWorld){
        //statement
    }

    //Good
    var helloWorld = 'helloWorld';

    if(helloWorld) {
        //statement
    }
    
    //example2
    
    //Bad
    var helloWorld = 'helloWorld',
        helloWroldCount = helloWorld.length;

    for(var i = 0; i < helloWroldCount; i++){
        //statement
    }
    
    //Good
    var helloWorld = 'helloWorld',
        helloWroldCount = helloWorld.length;

    for(var i = 0; i < helloWroldCount; i++) {
        //statement
    }

````

#### 소괄호
소괄호 시작[(]이전에 공백은 사용하지 않습니다.

````
    //example1

    //Bad
    var helloWorld = 'helloWorld';

    if (helloWorld) {
        //statement
    }

    //Good
    var helloWorld = 'helloWorld';

    if(helloWorld) {
        //statement
    }
    
    //example2

    //Bad
    var helloWorld = 'helloWorld',
        helloWroldCount = helloWorld.length;

    for (var i = 0; i < helloWroldCount; i++) {
        //statement
    }

    //Good
    var helloWorld = 'helloWorld',
        helloWroldCount = helloWorld.length;

    for(var i = 0; i < helloWroldCount; i++) {
        //statement
    }

````

#### 물음표
물음표에 앞뒤 공백을 넣습니다.

````
    //Bad
    var helloWorld = 'helloWorld';

    (helloWorld === 'helloWorld')?true : false;

    //Good
    var helloWorld = 'helloWorld';

    (helloWorld === 'helloWorld') ? true : false;
````

#### 콜론
콜론에 앞뒤 공백을 넣습니다.

````
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

    (helloWorld === 'helloWorld')?true : false;
````

#### 세미콜론

명령문 종료시 반드시 세미콜론을 기입합니다.
````
    //Bad
    var helloWorld = 'helloWorld'


    //Good
    var helloWorld = 'helloWorld';
````

의미없는 세미콜론을 사용하지 않습니다.
````
    //Bad
    ;function helloWorld() {
        //statement
    }


    //Good
    function helloWorld() {
        //statement
    }

````

변수선언을 제외한 중괄호 마침[}]뒤에 세미콜론을 넣지 않습니다.
````
    //Bad
    function helloWorld() {
	//statement
    };

    //Good
    function helloWorld() {
	//statement
    }
    
    //Good
    var helloWorld = function() {
	//statement
    };

````

#### 연산자
연산자를 쓸때 앞뒤 공백을 사용합니다.

````
    //Bad
    var helloWorld=1;

    //Good
    var helloWorld = 1;
````

##### 증감 연산자
증감 연산자는 앞뒤 공백을 사용하지 않습니다.

````
    //Bad
    var helloWorld = 1;

    helloWorld ++;

    //Good
    var helloWorld = 1;

    helloWorld++;
````

##### 복합 대입 연산자
````
    //Bad
    var helloWorld = 1;

    helloWorld = helloWorld + 1;

    //Good
    var helloWorld = 1;

    helloWorld += helloWorld;
````

##### 비교 연산자
삼항연산자를 기본으로하며 상황에따라서 다르게 써도 됩니다.

````
    //Bad
    var helloWorld = 'helloWorld';

    if(helloWorld == 'helloWorld') {
	//statement
    }

    //Good
    var helloWorld = 'helloWorld';

    if(helloWorld === 'helloWorld') {
	//statement
    }
````

특정값을 골라내야만 할때 빼고는 이 구문을 사용합니다.
````
    //example1

    //Bad
    var helloWorld = true;

    if(helloWorld === true) {
	//statement
    }

    //Good
    var helloWorld = true;

    if(helloWorld) {
	//statement
    }

    //example2

    //Bad
    var helloWorld = false;

    if(helloWorld === false) {
	//statement
    }

    //Good
    var helloWorld = false;

    if(!helloWorld) {
	//statement
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

````
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

````
    //Bad
    function helloWorld(nm,say) {
	return nm + ' : ' + say;
    }
    
    helloWorld('권정현','이건 자바스크립트 가이드야');

    //Good
    function helloWorld(nm, say) {
	return nm + ' : ' + say;
    }
    
    helloWorld('권정현', '이건 자바스크립트 가이드야');

````

### 이름

#### 변수
기본은 카멜 표기법입니다.

````
    //Bad
    var helloworld = 'helloWorld';

    //Good
    var helloWorld = 'helloWorld';
````

#### 상수
상수표기는 전체 대문자 + 스네이크 표기법으로 작성합니다.

````
    //Bad
    var helloWorld = 'helloWorld';

    //Good
    var HELLO_WORLD = 'helloWorld';
````

객체, 배열, 객체에 프로퍼티 이름은 상수를 사용하지 않습니다.
````
    //example1

    //Bad
    var HELLO = {};

    //Good
    var HELLO = {};

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

#### 은닉
변수에 할당된 값을 변경하지 말자는 약속이며 맨앞에 언더스코어를 붙여 작성합니다.

````
    //Bad
    var helloWorld = 'hellowWorld';

    //Good
    var _helloWorld = 'helloWorld';
````

상수와 은닉은 섞어 사용하지 않습니다. 상수는 값이 변할 수 없다는 의미를 가지고 있고 은닉은 값이 숨겨져 할당된 값을 수정할 수 없는 위치에 있는것입니다.
````
    //Bad
    var _HELLO_WORLD = 'helloWorld';
    
    //Good
    var _helloWorld = 'helloWorld';

    //Good
    var HELLO_WORLD = 'helloWorld';
````

#### 생성자
파스칼 표기법으로 작성합니다.

````
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
#### 용어

##### 축약

축약 전 이름 | 축악 후 이름 | 설명
| :------- | :------- | :-- |
name | nm | 이름
fn | function | 함수
temp | tmp | 임시
result | rst | 결과
global | g | 전역
index | idx | 인덱스
count | cnt | 카운트
length | len | 갯수

##### 단어

이름 | 설명
| :-- | :-- |
is | 있는지
has | 가지고 있는지
i ~ z | 루프 변수

#### 규칙
* 명사 + 명사
* 형용사 + 명사
* 명사 + 전치사 + 명사
* 명사

객체 프로퍼티명도 동일합니다.

#### 금지단어
<https://www.w3schools.com/js/js_reserved.asp>를 피해서 작성해야 합니다.

#### 축약
이름이 너무길어 축약이 필요한 경우는 음절로 축약하거나 주석으로 축약어를 제공하거나 누구나 알아볼 수 있어야 됩니다. 
````
    //before
    var functionType = typeof function() {};

    //after
    var fnType = typeof function() {};
````

### 생략

중괄호[{}]를 생략하지 않습니다.
````
    //example1

    //Bad
    var helloWorld = true;

    if(helloWorld)
        helloWorld = false;

    //Good
    var helloWorld = true;

    if(helloWorld) {
        helloWorld = false;
    }

    //example2

    var helloWorld = 5;

    for(var i = 0; i < helloWorld; i++) console.log(i);

    //Good
    var helloWorld = 5;

    for(var i = 0; i < helloWorld; i++) {
        console.log(i);
    }
````

한줄 if문에서 소괄호[()]를 생략하지 않습니다.
````
    //Bad
    var helloWorld = 'helloWorld';

    helloWorld === 'helloWorld' ? true : false;

    //Good
    var helloWorld = 'helloWorld';

    (helloWorld === 'helloWorld') ? true : false;
````

## 변수선언

여러번 선언하지 않는다. 상황에 따라서 분리가 필요할때 분리할 수 있습니다.
````
    //Bad
    var hello = 'hello';
    var world = 'world';

    //Good
    var hello = 'hello',
        world = 'world';
````

선언 키워드 없이 변수 선언을 해서는 안됩니다.
````
    //Bad
    helloWorld = 'helloWorld';

    //Good
    var helloWorld = 'helloWorld';
````

undefined를 유도한 값이 아니라면 초기화를 해주며 예외가 있을경우 예외에 맞게 작성하면 됩니다.
````
    //Bad
    var hello = 'hello',
        world;
    
    world = 'world';

    //Good
    var hello = 'hello',
        world = 'world';
````

필요한 구문에서 변수할당하며 중복된 변수명은 상단에 선언합니다.
````
    //example1
    
    //Bad
    var hello = 'hello',
        world = undefined;

    if(hello) {
        world = 'world';

	hello += world;
    }

    //Good
    var hello = 'hello';

    if(hello) {
        var world = 'world';

	hello += world;
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
````

값에 따라 바뀌는 변수일때 구문입니다.
````
    //example1

    //Bad
    function helloWorld(say) {
	var result = say;

	if(!result) {
	    result = 'helloWorld';
	}

	return result;
    }
    
    helloWorld();

    //Good
    function helloWorld(say) {
	var result = say || 'helloWorld';

	return result;
    }

    helloWorld();
    
    //example2
    
    //Bad
    function helloWorld(say) {
	var result = say;

	if(!result) {
	    result = false;
	}

	return result;
    }
    
    helloWorld();

    //Good
    function helloWorld(say) {
	var result = say && false;

	return result;
    }

   helloWorld();
````

\#.length를 여러번 사용할때 변수에 담아 사용합니다.
````
    //Bad
    var helloWorld = 'helloWorld';

    for(var i = 0; i < helloWorld.length; i++) {
	//statement
    }

    //Good
    var helloWorld = 'helloWorld',
        helloWorldCount = helloWorld.length;

    for(var i = 0; i < helloWorldCount; i++) {
	//statement
    }

    //Good
    var helloWorld = 'helloWorld';

    for(var i = 0, helloWorldCount = helloWorld.length; i < helloWorldCount; i++) {
	//statement
    }
````

## 객체

리터럴 구문을 사용합니다.
````
    //Bad
    var helloWorld = new Object();

    //Bad
    var helloWorld = Object();

    //Good
    var helloWorld = {};
````

프로퍼티의 맨마지막 콤마는 적지않습니다.
````
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
````
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
````
    //Bad
    var helloWorld = new Array();

    //Bad
    var helloWorld = Array();

    //Good
    var helloWorld = [];
````

특정위치에 값을 넣어야할때 빼고는 항목에 대입하지않고 push메소드를 사용합니다.
````
    //Bad
    var helloWorld = [];

    helloWorld[helloWorld.length] = 'helloWorld';

    //Good
    var helloWorld = [];

    helloWorld.push('helloWorld');
````

배열을 복사할때는 이 구문을 사용합니다.
````
    //Bad
    var helloWorld = ['helloWorld1', 'helloWorld2', 'helloWorld3'],
        helloWorldCount = helloWorld.length,
	newHelloWorld = [];

    for(var i = 0; i < helloWorldCount; i++) {
	newHelloWorld.push(helloWorld[i]);
    }

    //Good
    var helloWorld = ['helloWorld1', 'helloWorld2', 'helloWorld3'],
        helloWorldCount = helloWorld.length,
	newHelloWorld = helloWorld.slice();
````

## 문자
````
    //Bad
    var helloWorld = new String('helloWorld');

    //Bad
    var helloWorld = String('helloWorld');

    //Good
    var helloWorld = 'helloWorld';
````

### parseInt 메소드
문자형에서 숫자형으로 변환할때 특정값을 유도할때 빼고는 parseInt메소드를 사용하며 10진법을 명시합니다.

````
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
````
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

````
    //Bad
    var helloWorld = new Number(1);

    //Bad
    var helloWorld = Number(1);

    //Good
    var helloWorld = 1;
````

## 불린
형변환이 필요할때 빼고는 아래 구문을 이용합니다.

````
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
````
    //Bad
    var helloWorld = function() {
	//statement
    };

    //Good
    function helloWorld() {
	//statement
    }
````

즉시실행함수는 이 구문을 사용합니다.
````
    (function() {
	//statement
    })();

    (function() {
	//statement
    }());
````

함수호출을 줄입시다.
````
    //Bad
    document.getElementsByTagName('body')[0].style.color = '#fff';
    document.getElementsByTagName('body')[0].style.backgroundColor = '#000';

    //Good
    var body = document.getElementsByTagName('body')[0];

    body.style.color = '#fff';
    body.style.backgroundColor = '#000';
````

result변수에 담아서 한번만 반환합니다.
````
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

오류를 유발할 수 있는 구문은 try catch finally를 이용하며 try 중괄호 마침[}]뒤에 catch또는 finally가 반드시 붙어야됩니다.
````
    //Bad
    function helloWorld(say) {
        var result = eval(hello + say),
	    hello = 'hello';

        return result;
    }
    
    helloWorld('World');

    //Good
    function helloWorld(say) {
        try {
	    var result = eval(hello + say);
	}catch(e) {
	    var result = say;
	}finally{
	    console.log('끝났다.');
	}
        
	var hello = 'hello';

        return result;
    }

    helloWorld('World');
````

try catch안에서의 전역함수는 익명함수로 작성합니다.
````
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
        this.helloWorld(say) {
	    return say;
	}
    }catch(e) {
        console.error(e);
    }

    //Good
    try {
        window.helloWorld = function(say) {
	    return say;
	}
    }catch(e) {
        console.error(e);
    }
````

오류 표출은 자유롭게 사용합니다.
````
    //Bad
    new Error('내용');

    //Good
    console.error('내용');

    //Good
    throw '내용';
````

### 규칙
* 동사 + 명사
* 동사 + 형용사 + 명사
* 동사 + 명사 + 전치사 + 명사
* 명사

## 제이쿼리

제이쿼리 엘리먼트 변수는 $로 시작합니다.
````
    //Bad
    var body = $('body');

    //Good
    var $body = $('body');
````

다수의 호출을 피하고 묶을 수 있는 메소드는 묶어 사용합니다.
````
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

## 기준
ecma-262 3rd edition, december 1999