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
  <br/>
  여기도 출력이 가능해요
</p>
```
와 같이 코드를 작성하면 된다.

###### 14번
meter 태그는 특정 범위 내에서의 스칼라 값, 또는 백분율 값을 나타내는 요소이다.

  - value : 
  `min`(측정 가능한 최솟값), `max`(최댓값), `low`, `high`, `optimum`, `form`

`minlenght`와 `maxlength`는 `input type` 지정 시, 텍스트 길이를 제한하는 최솟값과 최댓값으로 사용하는 속성이다.

>여기서 스칼라값이란 벡터와 달리 방향을 가지지 않고 크기만 갖는 물리량을 뜻한다. 벡터는 크기와 방향을 갖는다는 것이 두 개념의 차이