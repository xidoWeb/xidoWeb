# CSS
___
## css3의 개념 및 특징
  [css 기능작동 여부](http://caniuse.com)

___
## CSS2
___
  ### 선택자
  [css 선택자의 발전](http://css4-selectors.com/browser-selector-test/)
  [css4_브라우저 확인](http://css4.rocks/)

___
  ### 작성 방법(위치)
  ___
  #### 직접 작성하는 방법
```
 <!DOCTYPE html>
 <html lang="ko-KR">
  <head>
    <meta http-equiv="X-UA-compatable" content="IE-edge" />
    <meta charset="utf-8" />
    <style></style>
    <script></script>
  </head>
  <body>
  </body>
 </html>
```

___
#### 별도로 파일을 불러서 사용 1
```
 <!DOCTYPE html>
 <html lang="ko-KR">
  <head>
    <meta http-equiv="X-UA-compatable" content="IE-edge" />
    <meta charset="utf-8" />
    <link rel="stylesheet" href="-css 파일 경로-" />
    <script></script>
  </head>
  <body>
  </body>
 </html>
```
위코드에서 나와있듯 `link`코드를 작성하여 css를 분리 시킨다.
`<link rel="stylesheet" href="-css 파일 경로-" />`

___
#### 별도로 파일을 불러서 사용 2
```
 <!DOCTYPE html>
 <html lang="ko-KR">
  <head>
    <meta http-equiv="X-UA-compatable" content="IE-edge" />
    <meta charset="utf-8" />
    <style>
      @import url("불러올 파일의 경로");
    </style>
    <script></script>
  </head>
  <body>
  </body>
 </html>
```
위코드에서 나와있듯 `style`코드 내에서 `@import` 기능을 이요하여 css파일을 불러오는 방법.
`@import url("불러올 파일의 경로");`

___
### css를 이해하기 전에~ `Bootstrap`을 이용해 봅시다~!
Bootstrap ?: css를 좀더 편하게 작업을 할 수 있도록 돕는 framework
핵심: `class` 이름만을 활용해서 반응형 웹, 색상, 크기, 디자인
CDN(contents delivery network) 기능을 이용해야합니다!
(사실은 다운받아서 써도 됩니다!)
[bootstrap 사이트 바로가기](http://getbootstrap.com)
[bootstrap한글 사이트 바로가기](http://bootstrapk.com)

___
 ### 선택자
 1. 타입선택자(태그선택자)
```css
    body{}
    html{}
    h1{}
    h2{}
    p{}
    img{}
```
___
 2. 자손 선택자: `html body{}` 모양으로 태그와 태그사이에 띄어쓰기로 선택
 ```
  ul a{}
  ul li a span{}
  ul span{}
  ul.box span{}
 ```
___
 3. 자식 선택자: `html > body{}` 형식으로 태그와 태그사이에 &gt; 모양을 삽입하여 부모 자식의 관계를 형성
 ```css
  ul > li{}
  ul > li > a{}
  #wrap div>li a{}
 ```
 ___
 4. class선택자, id선택자: class `.` 기호, id `#`기호를 붙여사용한다.
```css
 .container{}
 .container>li{}
 div.container{}
 
 .active{background-color:#000; color:#aaa;}
 div.active{color:#fff;}
 p.active{color:#fa0;}
 li.active{color:#00a;}
  
 div#wrap{}
 #wrap{}
```
___
5. 가상선택자: 타입이나, id/class 등의 선택된것의 기능이나 상태를 변경할때
-  :hover(마우스 올렸을때)
-  :active(마우스 누르고 있을때)
-  :visited(방문한 기록이 있을때 , 주로 a태그가 사용): check
-  :checked, :selected
-  ::before{ content: " "; }
-  ::after{ content:" "; }
```css
 h1{color:#c99; font-size:2em;}
 h1:hover{color:#fff;}
 h1:active{color:#333;}
```
___
6. 전체 선택자
- `*`
 ```css
  *{width:100px;}
 ```

___
7. 속성 선택자(속성명이나 속성값을 판단하여 선택하는것)
- a[href="#"] // 속성값이 #인 것
- input[type="button"]
- a[href^="http"]  // http로 시작할 때
- a[href$="com"] // 속성값이 com으로 끝날 때
- a[href*="."] // 속성의 내용중에 .이 포함 되는 모든 것
- a[href!="#"] // 속성값이 #이 아닌 것 

```
<style>
 a[href$="com"]{ color:#fa0; }
</style>
<body>
  <a href="http://naver.com">naver</a>
  <a href="http://daum.net">daum</a>
  <a href="http://google.com">google</a>
</body>
```
___
  ### size &amp; unit

  #### size
  width:넓이
  min-width:최소 넓이
  max-width:최대 넓이
  height:높이
  min-height:최소 높이
  max-height:최대 높이
- 조건: 최소, 최대를 사용할때 무조건 기본형태를 취해야한다.
___
  #### 단위
  0: 크기값이 없다.
  none: 존재하지 않는다.
  auto: 자동
  1이상일경우에는 단위를 붙인다.
- px: pixel을 의미
   - pt: point
   - em: 상대크기값을 나타내는 단위 <br>  (단, 박스의 크기는 절대/ 폰트의 크기는 상대)
   - %: percent(상대크기)
   - rem: 최초의 조건에 맞춰 만들어지는 상대크기
   - vw: 화면(view)의 가로값(width)의 크기를 기준의 단위
   - vh: 화면(view)의 세로값(height)의 크기를 기준의 단위

___
  ### background
-   background-color
    - red | blue | gray | deepblue ......

    - \#000000

    - rgba(255,255,255,1)

    - hsla(360, 100%, 100%, 1)

      ​
- background-image
    - url( "이미지경로 및 파일이름.확장자명" )
    - linear-gradient(각도deg, 색상 위치%, 색상 위치% .....)
    - radial-gradient(색상 위치%, 색상 위치% .....)
- background-repeat
    - repeat(기본) | no-repeat | repeat-X | repeat-Y
- background-position
  - background-attatchment
    - fixed | scrolll
  - background-size
    - cover | contain | % | w%   y%

___
  ### display(basic) &amp; visibility
  #### display
- none
- block
- inline
- inline-block
___
  #### visibility
- visible
- hidden

___
 ### overflow (영역을 넘어갈때 숨김/ 스크롤/보이게할것인가?)
 ___
 #### overflow
- hidden
- auto
- scroll
 ___
 #### overflow-x | overflow-Y
- hidden
- auto
- scroll
___
  ### float & clear
___
#### float
-  left | right
#### clear
  - left | right | both
___
### margin &amp; padding &amp; border &amp; outline
___
#### margin(빈 여백)
```
 div{margin: 10px;}   // 전체에 10px 공간
 div{margin: 10px 20px;}  // 위아래 10px  좌우 20px
 div{margin: 5px 10px 20px;} // 위5px 좌우10px 아래20px
 div{margin:5px 10px 15px 20px;} // 위5px  오른10px  아래15px  좌20px
 div{margin: 0 auto;}  // 위아래 0, 좌우 자동(가운데배치) -  float과 같이 사용X
```
___
#### padding(자신의 부피를 늘려주는것)
```
 div{padding: 10px;}   // 전체에 10px 공간
 div{padding: 10px 20px;}  // 위아래 10px  좌우 20px
 div{padding: 5px 10px 20px;} // 위5px 좌우10px 아래20px
 div{padding:5px 10px 15px 20px;} // 위5px  오른10px  아래15px  좌20px
 div{padding: 0 auto;}  // 위아래 0, 좌우 자동(가운데배치) -  float과 같이 사용X
```

___
#### border(선의 형태를 갖추는것 - 크기0, 부피0)
- border-width
- border-style: solid | dashed | dotted | bridge
- border-color
- border-bottom | border-left | border-right | border-top
___
#### outline(선의 형태를 갖추는것 - 크기0, 부피x)
- outline-width
- outline-style
- outlind-color
- outline은 일부 방향만 설정하는 것은 없다!
- outline-offset( IE에서는 사용할 수가 없다. )
___
#### box-sizing(border/ padding사용시 안쪽으로 생성되도록...)
- box-sizing:content-box //기본
- box-sizing:border-box  // 안쪽으로 생성되도록 처리

___
### position
- position:relative  // 자신이 기준이되고, 위치를 이동처리 가능
- position:absolute  // 부모를 기준으로 이동할 할 수 있도록 처리
- position:fixed  // 브라우저의 고정된 위치를 잡는 기능
- position:static  // 기본형태(작성하지 않아도 되는 형태)
- z-index:int;   // 음수 또는 양수로 입력하여 z축의 위치를 잡을 수 있다(단위 X)
- top | left | right | bottom  // position:static 을 제외한 나머지 사용할 수 있다.

___
### font
- font-size
- font-style
- font-weight
- line-height
- font-family
- color
- letter-spacing
- word-spacing
- text-decoration
- text-transform
- text-align: left | right | center | justify
- vertical-align: top | baseline | middle (text-area, input)
__________
## CSS3
___
### 선택자
- :nth-child(){}  // 연속되어진 type상태에서 선택하도록 
    - :first-child{}
    - :last-child{}
    - :last-nth-child(){}
- :nth-of-type(){} // 같은 레벨상에서 동일한 type을 선택시
    - :fir-of-type(){}
    - :last-of-type(){}
    - :last-nth-of-type(){}
___
### font
#### webfont
___
### prefix : 머릿말(현재 권고로 되어있지않지만 기능은 존재할때 사용하도록 처리)
```  
  background-image:-webkit-radial-gradient();
  background-image:   -moz-radial-gradient();
  background-image:    -ms-radial-gradient();
  background-image:     -o-radial-gradient();
  background-image:        radial-gradient();
  
  
  -webkit-transform:rotate(45deg);
     -moz-transform:rotate(45deg);
      -ms-transform:rotate(45deg);
       -o-transform:rotate(45deg);
          transform:rotate(45deg);
```
___
### border-radius
___
### transform
___
### transition
___
### animateion
___________

___
