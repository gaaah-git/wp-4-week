# 4주차 레포트
## 단축키
```c
div.가흔 + <Tap>
---> <div class="가흔"></div>
```


## 스타일
```c
<!doctype html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>padding, margin 실습</title>
  
  <style>
    *
  </style>

</head>
<body>
  <div class="parent">
    <div class="child">Content1</div>
    <div class="child">Content2</div>
  </div>
</body>
</html>
```
스타일은 헤드부분에 있음!

## 박스 만들기
```c
width: 100px;
height: 400 px;
padding: 10px 20px
marging: 10px 20px 30px 40px;
border: 1px black;
```
width 가로

height 세로


padding 내용과 테두리 사이 여백


marging 다른 박스와의 간격


border 테두리


상하 ---> 좌우


위 ---> 오른쪽 ---> 아래 ---> 왼쪽


; 잊지말기!

## ltr
```c
ltr
```
left to right: 왼쪽에서 오른쪽으로 읽는다는 뜻

## 오른쪽에 딱 붙는 박스 
```c
<style>
    nav.fixed {
       padding: 20px;
       position: fixed;
       top: 0; right: 0;
       height: 100%;
       background-color: gray; 
       color: white;
    } 
</style>
  .
  .
  .
<body>
       <nav>
       .
       .
       .
       </div>
</body>
```
박스색: 회색
박스안 글씨: 하얀색

## 박스안에 박스 넣기
```c
<style>
    .box {
      background-color: yellow
      padding: 
      margin:
    }
    .boox {
      background-color: orange
      padding: 
      margin: 
    }
</style>
    ...
<body>
  <div class="box">
     <div class="boox">노란박스 속</div>
     <div class="boox">오렌지 박스</div>
  </div>
</body>
```
노란 박스 속 오렌지 박스 두개

위에서 아래로 차곡차곡

## flex
```c
<style>
    .box {
      display: flex;
      width:
      background-color: yellow
    }
    .boox {
      width: 
      margin: 10px;
      background-color: red
    }
  </style>
</head>
<body>
  <div class="box">
    <div class="boox">속상자 1</div>
    <div class="boox">속상자 2</div>
    <div class="boox">속상자 3</div>
  </div>
</body>
```
|박스|박스|박스|박스|박스|
|----|----|----|----|----|
박스|속상자1|속상자2|속상자3|박스|
박스|박스|박스|박스|박스|


박스 속 속상자 3개 (가로로 쌓기, 왼쪽 여백 맞춤)

## display: flex; 로 하고
```c
flex-direction: column; (속상자 세로로 쌓기)
justify-content: flex-end; (속상자들 오른 여백 맞추기)
justify-content: center; (속상자들을 가운데에 배열, 이때 속상자들 사이 간격은 설정값)
justify-content: space-around; (속상자들을 가운데에 배열, 이때 속상자들 사이 간격은 모두 같음, 
                                 첫번째 속상자와 마지막 속상자 모두 사이드에서 떨어져 있음)
justify-content: space-between; (속상자들을 가운데 배열, 이때 첫번째와 마지막 속상자는 사이드에 붙어있음)
align-items: stretch; (속상자들 키 쭉쭉 ,height가 무시됨)
```

##  grid
```c
<style>
    .container {
      display: grid;
      grid-template-rows: repeat(4, 100px); 
      grid-template-columns: repeat(3, 100px);
    }
  </style>
</head>
<body>
  <div class="container">
    <div>box 1</div>
    <div>box 2</div>
    <div>box 3</div>
    <div>box 4</div>
    <div>box 5</div>
    ...
    <div>box 12</div>
  </div>
</body>
```
컨테이너 속



box1|box2|box3|
----|----|----|
box4|box5|box6|
box7|box8|box9|
box10|box11|box12|


```c
<style>
    .container {
      display: grid;
      grid-template-rows: repeat(3, 100px); 
      grid-template-columns: repeat(3, 1fr);
      grid-template-areas:
        "header header header"
        "section section aside"
        "footer footer footer";
    }
    header {
      grid-area: header; background-color: orange; }
    section {
      grid-area: section; background-color: #eee; }
    aside {
      grid-area: aside; background-color: greenyellow; }
    footer {
      grid-area: footer; background-color: yellow; }
  </style>
</head>
<body>
  <div class="container">
    <header>Header</header>

    <section>Section</section>
    <aside>Aside</aside>
    <footer>Footer</footer>
  </div>
</body>


```
header|header|header|
----|----|----|
section|section|aside|
footer|footer|footer|

