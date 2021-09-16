# :bookmark: 애매하게 알고 맞은 문제도 틀린 문제라도 생각하고 짚고 넘어가기

## 온라인 FE HTML/CSS 정기 테스트 from ZB 오답 정리

### ✔️210902 1회차

###### 1번. HTML 스타일 가이드에 적절하지 않은 것은?

html 기초 지식을 묻는 문제.
결과적으로 html에서는 대소문자를 구별하지 않기 때문에 <u>'2. element 내용은 상황에 맞게 대소문자를 사용'</u>은 옳지 않은 내용이다.

```html
<!-- html 기본 구조 -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title></title>
  </head>
  <body></body>
</html>
```

<br/>

###### 4-1번

title 속성에 대한 문제
HTML title 속성은 툴팁 기능을 구현하는 반면에 title 태그는 웹페이지의 제목을 브라우저 상단에 표시하는 기능을 한다. 즉, title 요소는 태그와 속성으로 사용될 때 삽입 위치와 기능이 전혀 달라진다는 것.
![](https://lh4.googleusercontent.com/2XNyu5IdqWpV31InVp5veAvZw7zbELI3w2notXyjYUH-IP_nAg3KEx54Ab_NeiFf4MZvGBdjLqEZh5sDjPOJAqcE7bdeOBkSHFvWEG6r5ObhmUKux-p4oCVRo-u3QgRbVA=w740)

위와 같이 만들고자 한다면

```html
<p title="툴팁입니다">
  툴팁을 위한 예제입니다.
  <br />
  여기도 출력이 가능해요
</p>
```

와 같이 코드를 작성하면 된다.

###### 14번

meter 태그는 특정 범위 내에서의 스칼라 값, 또는 백분율 값을 나타내는 요소이다.

- value :
  `min`(측정 가능한 최솟값), `max`(최댓값), `low`, `high`, `optimum`, `form`

`minlenght`와 `maxlength`는 `input type` 지정 시, 텍스트 길이를 제한하는 최솟값과 최댓값으로 사용하는 속성이다.

> 여기서 스칼라값이란 벡터와 달리 방향을 가지지 않고 크기만 갖는 물리량을 뜻한다. 벡터는 크기와 방향을 갖는다는 것이 두 개념의 차이

<br/>
<br/>

### ✔️210909 2회차

###### 5번

> div class 속성으로 my-bg라는 이름을 가진 것 위에 마우스를 클릭했을 때, 배경색을 빨간색으로 변경하기 위한 css를 작성하시오.

문제의 해석의 여지가 여러 가지로 나뉜다.

1. 답안 기준
   `.my-bg:hover { background-color : red; }`
   <br/>

2. '클릭'했을 때를 클릭하는 동안에만 스타일을 적용하고 마우스 클릭 뗐을 땐 스타일 비활성화
   `.my-bg:active { background-color : red; }`
   <br/>

3. 정석 css+js

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <div class="div1">
      <div class="clickmotion">div2_1</div>
      <div class="clickmotion">div2_2</div>
      <div class="clickmotion">div2_3</div>
    </div>
  </body>
</html>
```

```css
.div2 {
  border: 1px solid;
  width: 100px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.clicked {
  color: gold;
}
```

```js
let clickmotion = document.getElementsByClassName("clickmotion");

function handleClick(event) {
  console.log(event.target);
  console.log(event.target.classList);

  if (event.target.classList[1] === "clicked") {
    event.target.classList.remove("clicked");
  } else {
    for (let i = 0; i < clickmotion.length; i++) {
      clickmotion[i].classList.remove("clicked");
    }
    event.target.classList.add("clicked");
  }
}

function init() {
  for (let i = 0; i < clickmotion.length; i++) {
    clickmotion[i].addEventListener("click", handleClick);
  }
}
init();
```

<br/>
<br/>

###### 10번 속성 선택자와 클래스 선택자를 모두 사용해 작성해주시오.

사실 이 문제는 문제 제대로 안 읽고 지문만 읽어서 틀린 문제..

> class="check"로 되어 있는 모든 <input type="checkbox"> 요소의 스타일을 선택하려면 어떤 Selector를 사용해야할 지 작성하시오.

여기에서 우선 atrribute 선택자 개념 적용

> a[target] : a 태그 중 target 속성을 가지고 있는 요소 선택자
> a[target="_blank"] : a 태그 중 target 속성을 가지고 있으며 속성값이 "\_blank"를 가지고 있는 요소 선택자
> div[class^="start"] : div 태그 중 class 값이 "start"로 시작하는 요소 선택자
> div[class$="end"] : div 태그 중 class 값이 "end"로 끝나는 요소 선택자
> div[class*="wow"] : div 태그 중 class 값에 "wow"를 포함하고 있는 요소 선택자

위의 내용을 토대로 작성하면 input[type="checkbox"] .check

<br/>
<br/>

###### 17번

`clip-path`의 개념에 대해서 묻는 문제
`clip-path`란 요소의 클리피 범위를 지정하는 속성으로, 클리핑 범위 안의 부분은 보여지고, 바깥은 숨겨진다.

이 잘리는 부분을 `circle`과 같이 정해진 도형 키워드값으로 지정해줄 수 있지만 개발자의 의도대로 세밀하게 작성이 가능하다.

```css
div {
  clip-path: polygon(0 0, 0 100%, 100% 100%, 100% 55%, 55% 0);
}
```

> 마우스로 드래그해서 clip-path 값을 생성해주는 사이트 https://bennettfeely.com/clippy/
