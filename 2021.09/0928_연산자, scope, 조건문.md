### 11. 형 변환
- JS는 느슨한 타입 언어 혹은 동적 타입 언어
- 암묵적 형 변환을 수행
- 강제적 형 변환을 위해서는 자료형 함수를 이용해 명시적 형 변환을 수행하도록 함
- 다양한 객체 간의 형 변환이 필요한 경우에 형 변환 작업을 수행해줘야 함

#### String 변환
```js
console.log(String(123));
console.log(String(1/0));
console.log(String(-1/0));
console.log(String(NaN));
```

#### Number 변환
```js
console.log(Number(""));
console.log(Number("123"));
console.log(Number(1/0));
console.log(Number(-1/0));
console.log(Number("halo"));
console.log(Number("true"));
console.log(Number("null"));
console.log(Number("undefined"));

console.log(parseInt("123.123")); //output: 123
console.log(parseFloat("123.123")); //output: 123.123
```

#### boolean 변환
```js
console.log(Boolean(""));
console.log(Boolean("123"));
console.log(Boolean(1/0));
console.log(Boolean(1));
console.log(Boolean(0));
console.log(Boolean(false));
console.log(Boolean(null));
console.log(Boolean(undefined));
```

### 12. 산술대입 연산자
#### 연산자
- 프로그램에서 데이터를 처리하여 결과를 산출할 목적으로 사용되는 문자
- 연산의 대상 값은 피연산자라고 함
- 피 연산자의 개수에 따라 단항/ 이항/ 삼항 연산자 종류 존재

#### 연산자 우선순위
![](https://t1.daumcdn.net/cfile/tistory/997A014D5A90B9B00D)

#### 산술 연산자
수학적 계산을 위해 제공하는 연산자
```js
console.log(31 + 10);
console.log(31 - 10);
console.log(31 * 10);
console.log(31 / 10);
console.log(paesrInt(31 / 10));
console.log(31 % 10);
console.log(31 % 10);
```

#### 대입 연산자
```js
let num_1 = 123;
let num_2 = 456;
let str_1 = "hello";
let str_2 = "world";

let num_3, str_3;

num_3 = num_1 + num_2;
str_3 = str_1 + str_2;

console.log(num_3);
console.log(str_3);
```

#### 복합 대입 연산자
```js
let num = 10;

let result_1, result_2, result_3, result_4, result_5;
result_1 = result_2 = result_3 = result_4 = result_5 = 31;

result_1 += num;
console.log(result_1);

result_2-= num;
console.log(result_2);

result_3 *= num;
console.log(result_3);

result_4 /= num;
console.log(result_4);

result_5 %= num;
console.log(result_5);
```

#### 증가/ 감소 연산자
- 숫자 1만큼 증가 혹은 감소 시킬 때 사용되는 연산자
- 증가 연산자 : ++(피연산자), (피연산자)++;
- 감소 연산자 : --(피연산자), (피연산자)--;
```js
let num, result;

num = 10;
result = num++;
console.log(result); // num을 result에 복사된 후에 num의 값이 증가되므로 output 10
console.log(num); // output : 11

num = 30;
result = ++num;
console.log(result); // 11
console.log(num); // 11

num = 30;
result = num--;
console.log(result); // 10
console.log(num); // 9

num = 30;
result = --num;
console.log(result); // 9 
console.log(num);  // 9
```

### 13. 비교논리 연산자
#### 비교 연산자
- 좌항과 우항의 피연산자를 비교한 다음 결과값을 논리적 자료형으로 반환하는 연산자
- `==`은 단순값의 같음을 비교하는 동등 비교, `===`는 자료형까지 같음을 판단하는 일치 비교 연산자

#### 논리 연산자
- &&(AND), ||(OR), !(NOT)
![논리연산자](https://miro.medium.com/max/1400/0*YH506ZYL1rLNKQiK.)

### 14.SCOPE
- 변수 혹은 상수에 접근할 수 있는 범위
- 모듈/ 함수 내 코드에서 동일한 변수 사용시 간섭을 줄이는 용로도 사용
<br/>

1. Global Scope : 전역에 선언, 어디에서나 접근 가능
2. Local Scope(Block, Funtion level scope) : 특정 지역에 선언, 해당 지역 내에서만 접근 가능

![](https://media.vlpt.us/images/denmark-choco/post/4790583e-79be-4eda-8cb7-50a21ef64e97/scope.png)

```js
// global scope
let x = 1;
let y = 2;

{
  // local scope
  let x = 3;
  let y = 4;
  console.log(x);
  console.log(y);
}

function scope() {
  let x = 5;
  let y = 6;
  console.log(x);
  console.log(y);
}

console.log(x);
console.log(y);
```

#### block level scope 예제
```js
let index  = 1000;

function local_func() {
  let index = 100;

  for(let index = 0; index < 10; index++) {
    console.log(index);
  }
  console.log(index);
}

local_func();
console.log(index);
```

### 15. 조건문
#### 조건문 if-else
- 알고리즘에서 논리적 비교를 할 때 사용되는 조건식
- if, if else, else 키워드를 통해 구성되며, 조건식에 맞을 경우 `{}` 내에 있는 명령문을 수행
- 단, 실행 문장이 단일 문장인 경우에는 {} 생략 가능

```js
let apple_price = 9;

if(apple_price >= 10) {
  console.log("I will not buy that one");
} else if (apple_price < 5){
  console.log("I WILL BUY ALL ON THE STORE!");
} else {
  console.log("normal :(");
}
```

#### 3항 연산자
- 변수= 조건식 ? 참일때 값:거짓일 때 값
```js
let age = 20;

// 조건문:if-else
if(age < 19 ) {
  msg = "The user is not an adult.";
} else {
  msg = "The user is an adult.";
} 

console.log(msg);

// 3항 연산자
msg_another = age < 19 ? "The user is not an adult." : "The user is an adult.";
console.log(msg_another);
```

### 16.  조건문 switch
- switch는 표현식을 평가하여 그 값이 일치하는 case 문을 실행하는 조건문
- switch, case, break, dafault 키워드를 통해 구성되며, switch의 조건에 맞는 case구문을 수행
- 일반적으로 하나의 case만 수행되도록 case 끝을 break로 끝맺음
- 복수의 if 조건문을 switch문으로 바꿔 사용하는 것
```js
switch(x) {
  case 'value1':  // if (x === 'value1')
    ...
    [break]

  case 'value2':  // if (x === 'value2')
    ...
    [break]

  default:
    ...
    [break]
}
```

### 17.  연습 문제
```JS
// 조건문 switch를 이용하여 1~7 사이의 숫자를 입력 받으면 요일을 출력해주는 코드를 작성하시오
// 1(월요일)~7(일요일)로 맵핑

const DAY = 3;
let weekend = "";

switch(DAY) {
  case 1 :
    weekend = "MON";
    break;
  case 2 :
    weekend = "TUE";
    break;
  case 3 :
    weekend = "WED";
    break;
  case 4 :
    weekend = "THU";
    break;
  case 5 :
    weekend = "FRI";
    break;
  case 6 :
    weekend = "SAT";
    break;
  case 7 :
    weekend = "SUN";
    break;
}

console.log(weekend);
```
