# 오늘부터 한 번 시작한 챕터는 그날 무조건 끝내기
## 색상과 배경(이어서)
#### 5. background-position
<p ailgn="center">
  <img src="https://i.stack.imgur.com/FJ0JI.png">
</p>
배경이미지의 위치를 조정해주는 속성이다. 

  - 배경이미지의 왼쪽 꼭짓점을 기준으로 첫번째 값은 x축으로부터 떨어진 거리값, 다음 값은 y축으로부터 떨어진 거리값을 입력한다.
  - 영역 밖으로 배경이미지의 위치가 배치되면 이미지는 보이지 않게 된다.
  - `repeat`을 설정하면서도 이미지의 센터를 이동하면서 배경이미지의 배치를 조정할 수 있다.
  - 키워드도 값으로 사용 가능.
  `background-position: certer;`
  - 키워드로 값을 작성해줄 시, 키워드를 주는 순서는 상관이 없다.
  - 키워드를 주지 않는 쪽은 자동으로 가운데 정렬이 된다. 키워드를 하나만 줄 수도 있다는 뜻 (여러 개 작성해보면 뭔 말인지 앎..)

#### 6. background-origin
배경의 원점을 `content`, `border`, `padding` 중 하나로 지정한다.

  - value : `border-box`, `content-box`, `padding-box`(초기값)
  - 마진은 외부 여백이기 때문에 해당 속성값(margin-box 존재 x)으로 이용할 수 없다.

#### 7. background-size
배경이미지의 사이즈를 조정하는 속성.

  - value : `auto`(초기값), `contain`, `cover`, 숫자값, %
  -`cover`와 `contain`은 이미지의 비율을 유지할 수 있다.
  - `cover`은 이미지가 찌그러지지 않을, 컨테이너를 꽉 채우도록 이미지가 확대되어 가득 채운다.  *빈 공간이 없다는 것이 특징*
  - `contain`은 컨테이너 영역 안에 이미지가 잘리지 않을 정도, 딱 맞도록 이미지 크기를 조정한다.
  - 값을 하나만 입력하면 비율을 유지하면서 가로 사이즈만 지정이 가능하다. %도 비율 유지 가능.

#### 8.background(shorthand)
<p ailgn="center">
  <img src="https://devrix.com/wp-content/uploads/2015/07/background-property.jpg">
</p>

 - `background-attachment/clip`은 사용 빈도 수가 낮은 속성으로, 나중에 따로 체크해보면 좋다.
 - `background-color`는 무조건 뒤에 작성!
 - 입력하지 않은 값은 initial, 초기값을 따라가기 때문에 각 속성의 초기값을 알고 있는 것 또한 중요하다.

## Transform(변형)
#### 1. transform?
 원래 요소의 형태를 값을 주어 변형시키는 속성.
 - 원본 파일의 자리는 유지하되, 그 상태에서 형태를 변형 가능
 - `transform`은 `background` 속성과 달리 단 하나의 속성에 값을 변환시켜주어 요소를 변형시켜준다.
 - 오른쪽 값부터 왼쪽값으로 순차적으로 기능이 적용 (오른쪽에서 왼쪽!)
 - value : `none`(초기값), `scale`, `rotate`, `translate`, `skew`, `transform-origin`..

 기본적으로 transfrom 속성은 **레이아웃은 유지**하되, 요소의 형태를 **변형**시킨다는 성질을 가지고 있다는 것이 다른 속성들 간의 차별점이다.

 >참고 https://rgy0409.tistory.com/2990
 
#### 2. 크기 - scale
크기 조절. 현 강의에서는 2차원적인 value만 다룬다.
  - 1-2개의 값을 작성
  - number 사용. (integer는 정수값만 지칭, number는 소수점 숫자까지 포함)

```css
#disney {
  width: 200px;
  transform: scale(0.5);
}
```
  - `width` 와 `transform: scale()`은 동일한 듯 하지만 완전히 다른 개념. `transfrom: scale()`은 사이즈만 줄어들고 그 전의 레이아웃은 그대로 유지된다.
  - 괄호 안의 숫자값만큼 이미지 크기에 배수가 적용된다.
  - 값을 하나만 작성하는 방법, 두 개를 작성하는 방법이 있다.  
  - `scaleX`는 가로만 변형, `scaleY`는 세로만 변형

#### 3. 회전 - rotate
요소를 회전 시키는 속성
  - `rotate`를 이해하기 위해서 `angle` 개념을 짚고 넘어가자면, 각에 대한 표현을 뜻한다.
  - `angle` Unit
    - deg : 각도. 45도 = 45deg
    - turn : 1trun = 1바퀴 
    `90deg = 100grad = 0.25turn = 1.5708red`
  
  *memo*.자료형이란?

#### 4. 이동 - translate
<p align="center">
  <img src="https://res.cloudinary.com/practicaldev/image/fetch/s--PlbWbs7V--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tkbkgh1fkc2ik20u1cw5.png">
</p>
요소를 지정한 위치로 X 또는 Y축만큼 이동

```
transform:translateX(10px);        // X축으로 10px 이동
transform:translateY(10px);        // Y축으로 10px 이동
transform:translate(-10px, -10px); // X축으로 -10px, Y축으로 -10px 이동
```
  - 괄호 안의 하나의 값을 입력하면 남은 값은 자동으로 0이라고 취급된다.
  - 첫번째 값이 가로, 두번째 값이 세로로 이동하는 좌표의 값

#### 5. 기울이기 - skew
`rotate`와 유사한 듯 보이지만 '비틀다'라는 뜻과 다른 기능을 가지고 있는 속성
  - `90deg`로 값을 주면 완전히 일자로 비틀어지기 때문에 보이지 않게 된다.
  - 회전 속성과 달리, 형태와 각도가 동시에 변형된다.

#### 6. 기준점 - transform-origin
`transform`이 적용될 때 기준이 되는 기준점을 설정하는 속성. 
  - 원점을 결정. 원점에 따라서 변형되는 결과가 달라진다.
  - 초기값은 `transform-origin : center;`
  - 후에 `trasition`이나 `animation`을 지정해주면 움직이는 경로를 가시적으로 표현 가능하기 때문에 이 때, 유용하게 사용이 가능하다.
