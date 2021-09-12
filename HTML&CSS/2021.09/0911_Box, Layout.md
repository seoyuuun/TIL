## Box model (이어서)
#### 8. 테두리 - border-style, border-width, border-color
`padding`과 `margin` 사이의 테두리

- `border-style` (`border-width`, `border-color` 동일)
    - 테두리를 만들 수 있는 3가지 속성. 단축 속성(shorthand)
    - `none`(기본값), `soild`를 가장 많이 사용
    - `border-style` 속성은 1-4개의 값을 사용해 속성 지정 가능
        - 시계방향, 하나작성은 전역으로, 두 개 작성은 가로/세로

#### 9. 테두리 - border(shorthand)
테두리 또한 여백과 같이 단축 속성으로 작성이 가능하다.
- 8의 속성들은 다 `optional`, 그러나 스타일을 지정하지 않으면 기본값이 `none`이 사용돼 테두리가 보이지 않는다.
- 순서는 원하는대로 작성 가능하지만 일관성을 지키는 것을 권장
>**테두리(border) vs 외곽선(outline)**
두 속성이 매우 유사하지만 외곽선은 요소 콘텐츠의 밖에 그려지면 절대 공간을 차지하지 않는다는 차이가 있다. 즉, 외곽선은 박스 모델에 해당하지 않는다.

#### 10. 테두리 - border-radius
꼭짓점을 둥글게 만들어주는 속성. 속성값만큼의 반지름을 가진 원만큼 둥그런 정도가 조정된다.
- %를 사용할 경우, 가로와 세로에 각각 비율이 적용되기 때문에 필요에 따라 타원형으로 radius를 줄 수 있다.
- 단축 속성을 활용하여 네 꼭짓점 각각에 다른 값의 반지름의 크기를 가진 원으로 표현 가능하다.

#### 11. box-sizing
중요한 개념들 중 하나이다. 이를 이해하기 위해서는 박스모델의 개념을 정확히 숙지하고 해당 개념을 적용해야 한다. 요소의 너비와 높이를 계산하는 방법을 지정해주는 속성.
<p>
    <img src="https://miro.medium.com/max/2000/1*BrgpLX4k4FbFfJMyAqno-g.jpeg">
</p>

- 속성값은 `content-box`(기본값), `border-box`가 있다.
        - `content-box`는 기본 CSS 박스 크기 결정법을 사용한다. 요소의 너비를 100 픽셀로 설정하면 콘텐츠 영역이 100 픽셀 너비를 가지고, 테두리와 안쪽 여백은 이에 더해진다.
        - `border-box`는 테두리와 안쪽 여백의 크기도 요소의 크기로 고려한다. 너비를 100 픽셀로 설정하고 테두리와 안쪽 여백을 추가하면, 콘텐츠 영역이 줄어들어 총 너비 100 픽셀을 유지합니다. 대부분의 경우 이 편이 크기를 조절할 때 쉽다. 보통 `*` 선택자를 사용하여 최상단에 `boder-box`속성을 작성하는 경우가 많다.

## 레이아웃 Layout
#### 1. display - inline, block, inline-block
각 요소는 생성된 시점부터 인라인, 블럭, 인라인-블럭 속성을 가지고 생성된다. 이를 `display `속성을 이용하여 변경이 가능하다.

- `inline` 요소 : ex) `span`..
        - 영역의 크기가 내부 콘텐츠 크기로 정해진다.
        - `width`와 `height` 지정 불가능
        - `margin`, `padding`의 top/bottom 지정 불가능
        - 여러 요소가 가로로 배치 가능

- `block` 요소 : ex) `div`, `p`..
        - 영역의 크기를 `width`, `height` 지정 가능
        - `width`를 지정하지 않으면 가로 전체를 차지한다.
        - 여러 요소가 세로 배치가 된다.

- `inline-block` 요소 : ex) `input`..
        - 영역의 크기를 `width`, `height` 지정 가능 (like 블럭요소)
        - 여러 요소가 가로로 배치 가능 (like 인라인요소)

#### 2. 요소를 없애는 방법 - display none, visibility hidden
두 요소는 요소를 눈에 보이지 않게 없앨 때 사용이 가능한데, 두 요소는 중요한 차이점을 가지고 있다.
<p>
    <img src="https://pbs.twimg.com/media/EidMgQcXkAAgquP?format=png&name=large">
</p>
<p>
    <img src="https://pbs.twimg.com/media/EidMDMJX0AI93NZ?format=png&name=large">
</p>

- `display:none;`은 레이아웃, 콘텐츠 모두 제외시켜 눈에 보이지 않게 해 해당 속성을 작성한 영역의 빈 자리를 다른 영역이 채우는 반면에, `visibility:hidden;`은 콘텐츠는 사라지나 레이아웃은 그대로 유지해 해당 속성을 작성한 영역이 빈 영역으로 유지된다.
- 이 두 차이를 숙지하여 나중에 JS를 이용한 반응형 웹 사이트를 만들 때, 해당 영역의 레이아웃을 유지할지, 아닐지에 맞게 속성을 작성하도록 한다.

#### 3. float
단어 그대로 요소를 부동하도록 해주는 요소를 보통 흐름(normal flow)으로부터 빠져 텍스트 및 인라인 요소가 주위를 감싸는 자기 컨테이너의 좌우측을 따라 배치되도록 하는 속성
>보통 흐름(normal flow)란 개발자가 강제적으로 스타일, 혹은 명령을 주입하지 않았을 때, 자동적으로 CSS에 정의된 계산에 맞도록 코드를 진행하는 것
- 기본값은 `none`
- 기사나 article 같은 콘텐츠에 사용하는 경우가 많으며, 이미지를 삽입할 때 글과 어울리도록 하는 역할을 하기도 한다.
- flexbox가 등장한 이후부터는 사용도가 감소했으나, 사용 목적이 확실하면 효과적으로 사용 가능할 것이다.

#### 4-8. position
<p>
        <img src="https://media.vlpt.us/images/realryankim/post/a4aa7fe6-00ca-4cbf-89de-12be6eb374a3/blog-15-03-1.png">
</p>
요소가 원하는 위치에 배치할 수 있도록 지정하는 역할
- `position`에서도 `normal flow` 개념이 나오는데, 이를 이해하고 `position`이 어떻게 동작하는지 익히면 그 역할을 확실히 알 수 있다.
##### 1) 기본값 static
일반적인 문서 흐름에 따라 자연스럽게 레이아웃 배치. `position: static;`일 때는 top, botton, left, right 사용이 불가능 (값을 주더라도 이를 무시)
##### 2) relative
요소를 일반적인 문서 흐름에 따라 배치하고 **자기 자신**을 기준으로 오프셋을 적용. 각각의 방향을 기준으로 태그 안쪽 방향으로 이동한다. 바깥쪽으로 이동하게 하고 싶으면 음수값 작성.
top과 bottom 값을 동시에 작성하면 bottom 값을 무시, left와 right를 동시에 작성하면 right를 무시한다. (top, left 우선)
태그의 위치를 살짝 바꾸고 싶을 때 사용한다.
>relative 설명 중, 여기서 '자기 자신'이란 포지션이 static일 때는 지칭한다.

##### 3) absolute
일반적인 문서 흐름에서 제거된다는 것이 특징. **`static` 속성을 가지고 있지 않은 부모**를 기준으로 움직인다. 때문에 부모를 기준으로 이동한다.
만약 부모 중에 포지션이 `relative`, `absolute`, `fixed`인 태그가 없다면 가장 위의 태그(body-MDN에서는 초기 컨테이너 블록이라고 설명-)가 기준. *(강의에서는 조상 중에서 position이 static이 아닌 요소를 찾아 기준점을 찾는가도 설명)*
위
아래와 같이, 대부분 `position`이 `absolute`로 줄 경우, 기준점으로 삼고 싶은 부모 요소에 `position: relative;`로 설정한다.
```css
.parent {
  position: relative;
}

.child {
  width: 150px;
  height: 100px;
  border-color: blueviolet;
  border-radius: 30px;
  background-color: palegreen;

  position : absolute;
  top: 100px;
}
```
##### 4) fixed
기준점이 자기 자신, 부모 요소가 아니라 **뷰포트(viewport)**를 기준으로 삼는다. `absolute`와 달리, 뷰포트를 기준으로 하기 때문에 스트롤을 아무리 해도 지정된 자리에 그대로 유지된다.
붕 떠이는 버튼, 네비게이션 바 등을 만들 때 사용한다.

##### 5) sticky
평소에는 일반적인 문서 흐름을 따르다가 스크롤 위치가 임계점에 이르면 `position:box;`와 같이 화면에 고정하도록 하는 속성
반드시 스크롤 되는 부모의 하위에다가 작성을 해야 정상적으로 움직인다.

#### 9.overflow
콘텐츠가 바깥쪽 컨테이너보다 커서 넘쳐흐를 때 처리 방법을 지정하는 속성.
`visible`(그대로 노출), `hidden`(잘라내기), `scroll`(스크롤바 노출), `auto`(브라우저가 자동으로 값 지정) 지정 가능하며 그 기능은 단어의 뜻을 따른다.

#### 10. z-index
순서에 관한 개념. z축의 순서를 지정하는 속성...잠깐만 이거 구글 찬스 써야겠다
