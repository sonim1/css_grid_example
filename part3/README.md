# fr단위를 이용하여 grid 나누기

![grid3](/assets/grid3.PNG)

이번 코드에서 중요 포인트는 fr단위입니다.

[보기]()

아래 css를 보시죠

```css
.container {
    display: grid;
    height: 100vh;
    grid-template-columns: 1fr 4fr 1fr;
    grid-gap: 10px 100px;
    margin: 10px;
}

.grid-item {
    background-color: rgb(74, 173, 228);
}
```
`grid-template-columns`를 보시면 1fr + 4fr + 1fr => 총 6개의 fragment로 나눕니다.

데모를 보시면 바로 이해가 가실겁니다.

하지만 특이한 점이 있는데 `grid-gap`이 위에서 나눈 fragment별로 적용이 된다는 점입니다.