## Transition
#### 1. transition 개요
CSS 속성을 변경할 때 애니메이션 속도를 조절하는 방법을 제공. 
  - 속성 변경이 즉시 일어나지 않고, 설정한 일정 시간에 걸쳐 일어나도록 할 수 있다.
  - 형태의 변형 뿐만 아니라, 변형되는 시간 설정이 가능

#### 2-3. transition-property, transition-duration
`transition-property`는 CSS 속성을 어떻게 `transition` 할지는 지정해주고, `transition-duration`은 얼마의 시간동안 `transition`을 적용할지 시간을 지정해주는 속성이다.

#### 4. transition-deley, transition-timing-function
`transition-delay`, `transition-timing-function`는 각각 전환효과가 나타나기 전까지의 지연시간을 설정하는 속성, 전환 효과의 시간당 속도를 설정하는 속성이다.
  - 요소가 여러 개 있을 때, `transition-delay` 값을 활용해 도미노처럼 순차적으로 실행되는 효과를 줄 수도 있다.
  - `transition-timing-function`
    - value : `ease`(normal과 같은 느낌), `ease-in`, `ease-out`, `ease-in-out`, `linear`..

#### 5. transition (shorthand)
<p align="center">
  <img src="https://d33wubrfki0l68.cloudfront.net/02ca5906d1d4d7e7725e83029a0ff236a2756988/7b62e/images/css/back-to-basics-css-transitions/anatomy-of-transition.svg">
</p>

위의 4가지 속성은 서로 연관성이 강하기 때문에 `transition`을 단축 속성을 이용해 한 줄로 작성하는 것을 권장한다. 
  - 시간들과 연관된 `transition-delay`, `transition-timing-function`의 순서가 중요하며, `transition-property`를 가장 앞에 작성해준다.

## Animation
#### 1. 개요
유저의 액션이 있어야지만 움직이는 `transition`과 달리, `animation`은 별도의 액션이 없어도 움직인다.
  - 다수의 스타일 전환을 크리거를 사용해 유저의 액션에 맞춰 전환을 할 수도 있고, 별도의 액션이 없어도 자동으로 전환되도록 할 수도 있는 것이 `animation`
  - `animation`은 다수의 스타일 세트를 `keyfram`이라는 요소를 통해 어떤 스타일을 전환할 것인지 결정

#### 2. @keyframes
애니메이션 과정의 중간 절차를 제어할 수 있게 하는 규칙. 브라우저가 자동으로 애니메이션을 처리하는 것보다 세밀하게 조정 가능하다.

처음과 끝만 값을 설정할 경우,
```css
@keyframes myFirstAnimation {
  from { width: 100px;}
  to {width: 200px;}
}
```

2개 이상의 keyframe을 지정할 경우,
```css
@keyframes myFirstAnimation {
  0% {
    font-size: 20px;
  }
  50% {
    width: 500px;
    font-size: 50px;
  }
  100% {
    font-size: 20px;
  }
}
```

#### 3. animation-name, animation-duration
`animation-name`은 키프레임 애니메이션 이름을 지정하며, 특수문자를 제외한 문자열, 숫자, -,_ 를 조합해 1글자 이상으로 작성해야 한다는 규칙이 있다.
  - 기본적으로 상속이 되지 않으며, 되도록이면 상속을 할 수 없게 설정하는 것이 후작업에 헷갈리지 않을 것이다.
`animation-duration`은 애니메이션 키프레임이 한번 실행되는데 사용되는 시간을 설정한다.
  - 반드시 양수값을 값으로 작성해야 한다.

#### 4. animation-delay, animation-timing-function
`animation-delay`는 애니메이션이 시작하기 앞서서 지연되는 시간을 설정한다.
  - 음수값도 줄 수 있는데, 음수값을 줄 경우에는 음수값만큼 애니메이션이 실행된 것처럼 실행된다. 즉, -1s으로 설정하면 마치 1초 전에 애니메이션이 실행된 것처럼 1초 후 지점부터 애니메이션이 실행된다는 것
`animation-timing-function`은 `transition-timing-function`과 거의 동일하다.

#### 5. animation-interation-count, animation-direction
`animation-interation-count`는 애니메이션의 재생횟수를 설정한다.
`animation-direction`은 어떻게 애니메이션 방향을 진행할지를 설정한다.    
  - 정방향, 반대로, 왔다갔다가, 반대로 왔다갔다 ..

#### 6. animation-play-state
애니메이션이 실행 중이거나 일시 정지되어 있는지 여부를 설정한다. 예제 파일 Animation.css의 class 선택자 box4에서 이가 적용된 것을 살펴볼 수 있다.
```css
.box4 {
  width: 100px;
  height: 100px;
  background-color: skyblue;

  animation: rotate 2s infinite;
  animation-iteration-count: infinite;
  animation-direction: alternate-reverse;
  animation-timing-function: linear;
  animation-play-state: paused;
}

.box4:hover {
  animation-play-state: running;
}
```
위의 코드의 경우, 해당 스타일이 적용된 box는 hover될 때만 애니메이션이 적용되는 것을 볼 수 있다.

#### 7. animation-fill-mode
애니메이션이 실행되기 전과 후에 대상에 스타일을 어떻게 적용할 것인지 방법을 지정하는 속성
  - `none`, `forwards`, `backwords`, `both`
<p align="center">
  <img src="https://i0.wp.com/www.tutorialbrain.com/wp-content/uploads/2019/06/CSS-Animation-Fill-mode.png?fit=608%2C452&ssl=1">
</p>

  - none : 기본값
  - forwards : 마지막 프레임 유지
  - backwards : 처음에 적용된 스타일 값으로 유지
  - both : forwards와 backwards를 모두 유지

>CSS 애니메이션 쉽게 사용 가능한 온라인 툴 링크 https://nanati.me/css3-animation-tools/