# css 이해

## css란?

html 마크업되어져있는 내용(구조)을 꾸며주는 기능

> id => # | class => .

```html
<!-- html 문서의 <head>영역 내부에 css를 작성하기위한 영역 선언 -->
<style type="text/css">						/* html5 버전부터 ' text="text/css" ' 작성하지 않음
	/* 주석 */
	#box{
		color:#fa0;
		background-color:#0af;
	}
</style>							
<!-- css영역 종료	-->
```

------

## 선택자!

> 선택자란 body에있는 코드를 선택해서 어떠한 작업을 할 수 있도록 가능한 무언가..

- `.box{}` : class 선택자, `#box{}` : id 선택자

- `div{}` , `p{}`: element선택자/ type선택자

- `div li{}` : 자손선택자(해당 element 내부에 존재하는 element를 선택,위치는 정확하지 않다.)

- `div > ul > li{}` :자식선택자(element 내부(바로하위)에 존재하는 element 선택.)

- `a[href="#"] {}`: 속성선택자(해당 element의 속성 및 속성값을 선택해서 사용)

- `p.box{}` : element 자신을 선택할때 그 속성이 class="box" 인것

- `div#box{}` : element 자신을 선택할때 그 속성이 id="box" 인것(비추)

- 상태선택자

  - `code:hover{}`
  - `code:active{}`
  - `code:visited{}`
  - `code:focus{}`

- 가상선택자 : html문서내에 존재하지 않는 코드를 가상으로 생성하여 사용할수 있도록처리 

  - 리딩프로그램으로 읽어주거나 하는 문제가 없어, 접근성작업시 묵음으로 처리된다.(존재가 없는 형태)

  - `code::before{content:" ";}`  ie하위버전에서는  `:`을 하나만 사용
  - `code::after{content:" ";}` ie하위버전에서는  `:`을 하나만 사용

```
- a:hover{color:#000;} /* 마우스 올렸을때 */
- a:active{color:#fa0;} /* 마우스 누르고있을대 */
- a:visited{}/* 방문한 페이지 */
- a:focus{outline: 2px solid #000;}/* 활성화 되었을때 */
- a::before{content:"앞부분"; color:#777;}/* 내용의 앞부분(content로 추가삽입) */
- a::after{content:"뒷부분입니당."; color:#777;}/* 내용의 뒷부분(content로 추가삽입) */

```

------

## LAYOUT_basic

- `line-height`: 행간(줄간격)을 박스의 높이값 만큼 똑같이작성하면, 해당하는 텍스의 위치는 수직정력의 가운데 배치가 된다. (단, 한줄만 해당!!!)- 엄밀히 말하면 편법
- `display`: 각자 존재하는 element들의 고유 형태(inline, block)에 따라서, 디자인되는 모양이나, 위치가 변동될 수 있다. 하지만 inline형식이 block형식으로 변환되거나 그 반대상황으로 되어야할 경우가 있을때에는 강제 변환시키는 기능이 필요하다. 이 기능이 display속성이다.
  - `inline;` 크기값이 존재하지 않고, 줄바꿈이 일어나는 현상으로 치환
  - `block;` 크기가 존재하고, 줄바꿈이 일어나지 않는 현삭으로 치환
  - `none;` 존재자체가 사라지게 만드는(공간조차 없어지는) 속성값
  - `inline-block;` 크기값이 존재하며, 줄바꿈이 일어나는 현상으로 치환
- `visibility`: display 속성과 유사하지만 조금 다른성격이 있다.(block, none)
  - `visible;` display:block;or display:inline; 처럼 보이는 속성값
  - `hidden;` display:none;처럼 존재자체를 없애버리는 효과 (단, 위치하던 자리는 흔적이 남는다.)

------

## RESET.CSS

> 브라우저 마다 각기 다른 여백, 라인두께 등의 기능들이 내제되어있다. 이에 모든 브라우저를 똑같은 환경으로 설정하는것! **Reset.css**(하지만, ie8이하와 같은 구형브라우저에서는 reset.css의 단일기능만으로는 같은형태를 잡기가 쉽지 않다. 이에 **hack**이라고하는 별도의 기능을 사용하게 되어있다.!)

```
#box{width:300px;  _width:300px; *width:300px; } // hack 
```

> 모든 브라우에서 저마다 생기는 여백, 기타다향한 형태를 최초 설정시에는 *기호를 붙여 margin:0; padding:0; 이라는 속성을 만든다. (*의 뜻은 모든 element를 지칭한다.)

```
*{marign:0; padding:0;}

```

> 레이아웃디자인작업시 여러개의 반복모양이 나타난다면 list를 사용하는데 list 모양은 앞에 불릿기호들이 항상 존재하고있다.(ul,ol,li) 그래서 불릿기호를 삭제처리하려면 해당하는 스타일의 속성을 none시킨다.

```
ul,ol,li{list-style:none;}/* list-style*/


```

------

## margin, padding, border, outline

[![mpbo](https://github.com/xidoWeb/webStudy1603/raw/master/study/step_02_css_basic/img/readme/mpbo.jpg)](https://github.com/xidoWeb/webStudy1603/blob/master/study/step_02_css_basic/img/readme/mpbo.jpg)

### margin

> 여백: 바깥여백(공간 o), 부피o, 배경이 보인다.

- 자신과 다른 개체와의 공간을 만드는것
- 한쪽만 처리 가능하다.
- 한꺼번에 처리가 가능하다.
  - **margin:10px;** 위,아래,좌,우 모두 10px
  - **margin:10px 20px;** 위,아래 10px 좌,우 20px
  - **margin:10px 20px 30px;** 위 10px 좌,우 20px 아래 30px
  - **margin:10px 20px 30px 40px;** 시계방향으로 위10 우20px 아래30px 좌40px

### padding

> 여백: 안쪽여백(공간o), 부피o, 배경이 보이지 않는다.

- 자신의 부피가 늘어난다
- 한쪽만 처리 가능하다.
- 한꺼번에 처리가 가능하다.
  - **padding:10px;** 위,아래,좌,우 모두 10px
  - **padding:10px 20px;** 위,아래 10px 좌,우 20px
  - **padding:10px 20px 30px;** 위 10px 좌,우 20px 아래 30px
  - **padding:10px 20px 30px 40px;** 시계방향으로 위10 우20px 아래30px 좌40px

### border

> 외곽선: 자신의 외곽형태에 선의 모양을 만드는것 

- **border:1px solid #fac;**  외곽선을 한꺼번에 처리하기
- **border-weight:1px;**  외곽선 두께
- **border-style:solid | dotted | dashed | double....;**   외곽선 모양 
- **border-color:#fac;** 외곽선 색상


- 한쪽방향o, 부피o

### outline

> 외곽선: 형태나, 크기는 존재하지만 부피는 없다!

- 한쪽방향만 줄수는 없다!
- 주로 접근성을 위한 사용이 많다

------

## font

> font:서체 및 다야한 글씨에대한 내용을 표현하는 속성

- `font`:굵기 기울기 크기/행간 서체,서체,서체...;

  - font-weight:light | normal | bold | bolder | 100 ~ 900...
  - font-style: italic | normal
  - font-size: 100% = 1em = 1rem = 12pt = 16px
  - line-height: 1.2
  - font-family:"myriad pro", "arial", "맑은고딕";

- `color`: 글씨색

- `text-decoration`: underline | overline ...;

- `text-overflow`:ellipsis | clip;

  > ellipsis:지정된 크기의 글씨가 넘칠경우에 ...으로 표기 단, 감싸는 개체는 overflow:hidden;으로 처리해야한다.

- `letter-spacing`:  자간(글자와 글자사이 간격)

- `word-spacing`:  어간(단어와 단어사이 간격)

------

## position

- `static` : 기본
- `fixed` : 강제로 브라우저상에서 위치잡기
- `relative` : 무언가(absolute)의 기준일때
- `absolute` : fixed처럼 완전한 자유는 아니지만 원하는 위치를 정해서 배정가능

> static을 제외한 position 속성값은 다음과 같은 기능을 추가로 가진다.

- `z-index`:  " - " 값부터 사용이 가능하며, 단위 x, 앞뒤의 배치를 가진다.
- `top, left, right, bottom` 위치값을 가질수 있다.

------

## background

> background란? 배경이미지를 처리하는 속성 body영역에서 이미지를 담을때에는 img태그를 사용하는데, img 이미지위에 다른 글씨나 기타 여러 개체를 담을 수 없다!! 때문에 img태그대신에 배경이미지로 별도로 첨부하여 사용하는 방법

- `background`: url()   repeat   position;


- `background-color`
- `background-image`:url(); 이미지가져오면 자동으로 패턴
- `background-repeat`:repeat | repeat-x | repeat-y | no-repeat;
- `backgrouhd-position`:x축 y축;
  - center center | left top | -100px -200px;
- `background-attatchment`: scroll | fixed;

### IR 기법(image replace) : img태그 대체방법

1. 해당하는 개체는 block태그로 변환 (text-indent)
2. 단, 내부 텍스트의 경우 보이지 않게 처리
3. display:none or visibility:hidden의 경우는 동작하지 않으므로 다른방법으로 사용

### IS 기법(image splite) : ir기법 사용시 확장

1. 여러개의 이미지를 하나의 판에 모아놓고 필요한 부분을 바로 체크할 수 있도록 처리하는 방법
2. 작은 이미지 파일의 관리가 쉽다.
3. 주로 하나의 파일로 `background-position`을 활용하여 사용한다.