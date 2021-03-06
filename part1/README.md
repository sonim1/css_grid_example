# 들어가기 전
링크를 타고 오거나 중간부터 보셨다면 [시작하기](http://sonim1.tistory.com/193)를 먼저 보시길 추천드립니다.

# grid-area를 이용한 grid 나누기

첫번째 파트입니다.

간단하게 그리드를 구현해보겠습니다.

아래와 같은 Grid Layout으로 시작해봅시다.

![저장용](https://raw.githubusercontent.com/sonim1/css_grid_example/master/assets/0001.PNG)

[보기](https://rawgit.com/sonim1/css_grid_example/master/part1/index.html)

**index.html**
```xml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="../reset.css">
    <link rel="stylesheet" href="./grid.css">
    <title>Document</title>
</head>
<body>
    <div class="container">
        <header>Header</header>
        <nav>Nav</nav>
        <section>Section</section>
        <aside>Aside-right</aside>
        <footer>Footer</footer>
    </div>
</body>
</html>
```
간단한 구조로 되어있습니다.

`div.container` 안에는 `header, nav, section, aside, footer` 다섯 가지 레이아웃을 위한 시맨틱요소가 있습니다.

`head`에는 두 가지 css 파일을 가져오고 있는데 에릭 마이어의 css 초기화를 위한 reset.css 파일 그리고 grid 관련 스타일 시트를 불러오고 있습니다.

reset.css에 대해서는 [이 링크](http://meyerweb.com/eric/tools/css/reset/)를 참고하시고 우리는 바로 `grid.css`를 확인해봅시다.

```css
/* container init */
.container {
    display: grid;
    grid-gap: 5px;
    grid-template-areas:
    "header header header"
    "nav section aside"
    "footer footer footer";
}

/* All Grid Items */
.container > * {
    background-color: mediumseagreen;
    font-size: 80px;
}

header {
    grid-area: header;
}

nav {
    grid-area: nav;
}

section {
    grid-area: section;
}

aside: {
    grid-area: aside;
}

footer {
    grid-area: footer;
}
```

몇 가지 특징을 살펴봅시다.

우선 아래쪽을 보시면 시맨틱 별로 아래처럼 `grid-area`를 할당해주고 있습니다.
```css
header {
    grid-area: header;
}

...

footer {
    grid-area: footer;
}
```
여기서 할당해준 grid-area 명칭을 사용하여 grid를 나누게 됩니다.

```css
.container {
    display: grid;
    grid-gap: 5px;
    grid-template-areas:
    "header header header"
    "nav section aside"
    "footer footer footer";
}

```

1. `display`를 `grid`로 설정해줍니다.

2. `grid-gap`을 이용하여 각 그리드 간의 거리를 할당해 줍니다.

3. `grid-template-areas`를 이용하여 grid 구조를 할당하게 됩니다. (`grid-area`로 할당한 명칭사용)

위 코드를 보시면 열이 3개로 나뉘고
중간열은 3개의 열에 각각 다른 항목(`nav section aside`)이 들어가고 있습니다.
이 항목에서 사용되는 area 이름은 아래에서 grid-area 할당해준 이름입니다.

굉장히 직관적입니다.

# 마치며
CSS Grid Layout을 구성하는 첫번째 방법을 살펴봤습니다.
하지만 이는 시작일 뿐.. Layout을 구성하는 방법이 매우 다양합니다.
이후 포스트에서는 그런 여러가지 방법에 대해서 하나하나 이야기 해볼 예정입니다.
