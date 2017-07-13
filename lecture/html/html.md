___
# html
___
## entity code
특수문자를 바로 사용할수 없기때문에 그것을 코드화시켜 사용

- &amp; `&amp;`
- &copy; `&copy;`
- &lt; `&lt;`
- &gt; `&gt;`
- 빈칸 `&nbsp;`
- &quot; `&quot;`
- &apos; `&apos;`

___
## 구조화하기 1
___
### 기본 영역  
#### 제목을 표시하는 방법
`h$` : 1~6까지 존재

```html
<h1>가장 중요하고, 한번만(하나의 웹페이지) 사용 가능<h1>
<h2>두번째로 중요한 의미, h1의 하위 레벨의 의미 <h2>
<h3>세번째로 중요한 의미, h2의 하위 레빌<h3>
<h4>네번째로 중요한 의미, h3의 하위 레빌 <h4>
<h5>다섯번재로 중요한 의미, h4의 하위 레빌 <h5>
<h6>여섯번째 이자 가장 작은 단위의 영역 제목, h5의 하위 레빌 <h6>
```
___
#### 내용을 표시하는 방법
`p`: 내용(문단)
`pre`: 내용(문단) - 작성한 모양 그대로 표시!

`br`: 내용에서 줄을 바꾸는 기능

```html
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis nulla facere fugit,<br /> deleniti molestiae repellendus, excepturi sequi dicta quam fugiat nostrum dolorem voluptatem sed magni aut quos doloribus, laborum repudiandae.</p>
```

`hr`: 눈에는 라인이 형성, 실제의 의미는 내용(화제)전환
```html
<p>Lorem ipsum fugiat nostrum dolorem voluptatem sed magni aut quos doloribus, laborum repudiandae.</p>
<p>Lorem ipsum fugiat nostrum dolorem voluptatem sed magni aut quos doloribus, laborum repudiandae.</p>

<hr />			<!--  위내용과의 분리역할 -->

<p>Lorem ipsum fugiat nostrum dolorem voluptatem sed magni aut quos doloribus, laborum repudiandae.</p>
<p>Lorem ipsum fugiat nostrum dolorem voluptatem sed magni aut quos doloribus, laborum repudiandae.</p>

```

___
### list
 - ul: unorder 순서가 없다
   - li : 순서의 내용(리스트)
 - ol: order 순서가 있다
   - -li: 순서의 내용(리스트)
 - dl:  datalist data가 존재하는 리스트
   - dt: data 제목
   - dd: data 내용
___
### 그룹: 의미는 특별하게 없고, 영역을 뜻한다.
`div`: block 형식
`span`: inline 형식

___
**inline**
* inline 형식은 block 형식을 감쌀수 없다.
* 나열만 가능하다
*	기본적으로 사이즈를 가질 수 없다(일부 예외).
___
**block**
* inline형식을 감쌀수 있다, block형태도 감쌀 수 있다.
* 쌓여서 설정된다
* 크기를 가질 수 있다.
___
**inline-block**
* 사이즈를 가진다.
* 나열이 된다.
* 기본 속성은 inline을 따른다.

___
### 링크 &amp; 이미지
`a`: 앵커라고도한다. 기본속성 `href`, `target` 를 가진다. 
      - href: 
        1. #기호 사용시(임시링크), 
        2. http...(웹상의 주소-절대), 
        3. ./(상대경로), ../(상대경로)
      - target:
        1. _self : 현재띄워진 탭메뉴 실행(기본)
        2. _blank: 새창 띄워서 나타냄
        3. _top: 외부에서 문서를 불러왔을경우 최상단의 문서에서 변형
        4. _parent: 외부에서 문서를 불러왔을경우 부모영역에서

`img`: 이미지를 담는 태그(요소). 기본속성 `src`, `alt`
  -  src: 이미지파일의 경로
  -  alt: 이미지 설명  
	
	** 요소노드(element):태그, 속성노드, 텍스트노드를 모두 일컫는다.
___ 
### 이름지정하기(id, class)
  `id`: 한번만 지정한다, 연결의 의미, css에서`#`으로 앞에 표기  
  `class`: 여러번 사용 가능하다(공통 적용), css에서 `.`으로 앞에 표기
___
### 외부 문서 불러오기
`iframe` 외부의 문서를 불러와서 내문서에 삽입하는것!!! `src`, `frameborder`
___
### 테이블
table `summary`
caption
tr
th | td  `scope` `colspan` `rowspan`
thead 
tbody
tfoot
colgroup `span`
col `span`

___
### 폼
form `action` `method="get | post"` 
fieldset 
legend 
input `type`  `id` `name` `value`
label `for`
___
### input type
 -input:**type**
   1. 입력
    - text
    - password
___
   2. 선택
    - checkbox
    - radio
___
   3. 버튼
    - submit
    - button
    - reset
    - image  src=" " alt=" "
    - file
___
   4. 멀티(기타)
     - textarea name=" " id=" " readonly="readonly"
     - select(id=" " name=" ")/optgroup/option(value=" ")
     - button type=" "
___
## 구조화하기 2
___
### 블록구조화(시멘틱하게)
`header`
`aside`
`article`
`section`
`footer`
`main`
`hgroup`
`figure`



___
  ### video & audio
  
___
## etc
___
  ### meta
___
  ### entity code
___
  ### 조건부 주석
  
<!-- 
___
## 
___
### svg
___
### canvas
-->


___
[처음으로 돌아가기](./webStandard.md)