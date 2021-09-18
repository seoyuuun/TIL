## #2
#### 1-3. JS DataTypes(Super Simple. basic of basic)
- integer **정수**
- float **실수** *이런 타입이 있다를 이해하는 것이 요점*
- String **문자열**
	- `""` or `''`를 사용해 문자열이라는 것을 JS가 이해하게 작성한다.
	- 공백도 입력한 그대로 출력된다.

- varriable **변수**  -> 모든 프로그램에서 값을 저장하거나 유지하는 역할을 하는 값
on js, `const` or `let`이라는 단어를 사용
<br/>


>카멜표기기법 & 스네이크 표기기법(camel & snake case)
camel -> veryLong
snake -> very_long

- 변수를 만드는 두 가지 방법, `const` & `let` 차이점은?
	- `const`는 상수를 뜻하면 변경할 수 없는 값을 뜻함 ( 고정된 변수)
	- `let`은 필요에 의해 update 가능한 변수이며 `let`은 새로 만드는 첫 변수에만 붙고 이후, `let`이 선언된 변수값을 바꾸기 위해 해당 변수를 재사용할 때에는 `let`을 재선언하지 않는다.
		<u>`const`, `let` 이 두 개념의 차이를 통해 코드의 의미, 코드 제작자의 의도를 알 수 있음</u>
	
(Function)
part 1	
- function is piece of code what use again&again
- argument(인수) : function을 실행하는 동안 어떤 정보를 function에게 보낼 수 있는 방법

part 2
- 어떻게 데이터를 전송해서 함수가 받게 해 적용하는지 알아본다
	-> () 괄호 안에 인수를 입력해 해당 함수에 데이터를 전송한다
- argument는 지정된 function 안에서만 그 값이 유효
*NaN = Not a Number
- argument는 쉼표로 구분되며 순서대로 적용되기 때문에 순서가 중요

(Return)
console.log를 통해 console에서 결과를 기록해 코드가 의도대로 정상적으로 출력은 할 수 있으나 결과를 원하는대로 제공받을 수 없다


[HTML](https://github.com/seoyuuun/Normad-Coding/blob/main/index.html).
[JS](https://github.com/seoyuuun/Normad-Coding/blob/main/app.js).
[JS](https://github.com/seoyuuun/Normad-Coding/blob/main/app2.js).
