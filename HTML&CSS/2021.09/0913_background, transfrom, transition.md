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