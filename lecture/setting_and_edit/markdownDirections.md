## maek down

마크다운 (Markdown)은 마크업 언어의 일종으로, <br>
존 그루버(John Gruber)와 아론 스워츠(Aaron Swartz)가 만들었습니다. <br>
읽기도 쓰기도 쉽다는 장점이 있습니다. <br>
그루버는 마크다운으로 작성한 문서를 HTML로 변환하는 펄 스크립트도 만들었습니다. <br>
확장자는 **`.md`**를 씁니다.

--
### 제목(html의 `<h>`)

`# 텍스트`

`#`을 써서 html의 `<h1>`와 같은 방식으로 제목을 표현할 수 있습니다. 
`<h1>`~`<h6>` 까지가 있으므로 `#`도 6개까지 사용해서 제목을 표현하고,
`#`하나면 `<h1>`, `##`이면 `<h2>`를 의미하게 됩니다. **(# 뒤에 띄어쓰기 사용)**

```markdown
# h1

## h2

### h3

#### h4

##### h5

###### h6
```

# h1

## h2

### h3

#### h4

##### h5

###### h6

--
### 글꼴관련

##### 기울인 글씨 (html의 `<em>`)
```markdown
*텍스트* or _텍스트_
```
 *텍스트* or _텍스트_

##### 굵은글씨 (html의 `<strong>`)

```markdown
**텍스트** or __텍스트__
```
**텍스트** or __텍스트__

##### 취소선 (html의 `<del>`)
```markdown
~~텍스트~~
```
~~텍스트~~

##### 밑줄 (html의 `<ins>`)
```markdown
++텍스트++
```
++텍스트++

##### 원하는 문자 탈출시키기
\를 사용하면  backquote를 보이게 사용할 수 있다

```markdown

```
\`\`\`

\`\`\`



---

### 리스트관련

##### 번호 없는 리스트(각 내용은 탭키 또는 스페이스 두번의 기능으로 설정)
-/+/* 텍스트

~~~markdown
- 하나
  - 둘
    - 셋
~~~
- 하나
   - 둘
     - 셋


~~~markdown
+ 하나
  + 둘
    + 셋
~~~
+ 하나
   + 둘
      + 셋

~~~markdown
* 하나
  * 둘
    * 셋
~~~
* 하나
   * 둘
      * 셋

##### 번호 있는 리스트
숫자. 리스트

```markdown
1. 하나
2. 둘 
3. 셋
```

1. 하나
2. 둘
3. 셋

이런 방식으로도 쓸 수 있다. 

~~~markdown
// 예시1

 - 하나
   + 둘
     * 셋
~~~

- 하나
   - 둘
       - 셋

~~~markdown
// 예시 2

1. 일
2. 이
3. 삼
 - 하나
     + 둘
~~~

1. 일
2. 이
3. 삼
 - 하나
     + 둘


--
### 인용
```markdown
> 텍스트
인용문안에 인용문을 넣으려면 >를 더 추가해주면 된다.

> 문단을 두 개로 나누려면 한 줄의 공백을 주고 다시 >를 사용해 작성한다.
> > 인용은 이런 식으로도 사용할 수 있다. 
> > [링크 안걸려있어요][참조 1] 다른 마크다운 요소를 사용할 수 있다.
```
> 텍스트
> 인용문안에 인용문을 넣으려면 >를 더 추가해주면 된다.

> 문단을 두 개로 나누려면 한 줄의 공백을 주고 다시 >를 사용해 작성한다.
> > 인용은 이런 식으로도 사용할 수 있다.   
> > [링크 안걸려있어요][참조 1] 다른 마크다운 요소를 사용할 수 있다.

--
### 링크걸기

##### 인라인 링크
```markdown
[텍스트](링크주소)		// 방법 1
<링크주소>			  // 방법 2
```

[마크다운 참조](https://guides.github.com/features/mastering-markdown/)

##### 참조 링크
```markdown
[텍스트][참조 1]
[텍스트][참조 2]
[참조 1]: 링크주소
[참조 2]: 링크주소
```

[마크다운 참조1][참조 1]
[마크다운 참조2][참조 2]
[참조 1]: https://guides.github.com/features/mastering-markdown/
[참조 2]: https://guides.github.com/features/mastering-markdown/

##### 이미지(상대경로/절대경로 정확하게 표기하여 처리)
```markdown
![이미지 설명 텍스트](http://lorempixel.com/400/200/sports/1/)
```

![이미지보기](http://lorempixel.com/400/200/sports/1/)

--
#### 코드


\`코드 내용\`
`코드 내용`


\`\`\` 
코드 블럭
\`\`\`

```markdown
코드 블럭
```

코드 블럭에 강조 구문을 사용하고 싶다면, 사용하는 언어를 적어주자.

\`\`\`javascript

   function MyFn(n){
​    var myNum = n + 10;  
​    return myNum;
   }

 var myNum =   MyFn(10);

 console.log(myNum);


\`\`\`

```javascript
   function MyFn(n){
    var myNum = n + 10;  
    return myNum;
   }

 var myNum =   MyFn(10);
 console.log(myNum);
```


`space bar`를 4번 이상 치거나,  
`tap`키를 이용해 코드 블럭을 작성할 수도 있다.  
하지만, 눈에 명확하게 보이지 않으므로 쓰고싶지 않다.  

`tap` or `space bar`코드 블럭

```markdown
 코드 블럭
```
---

#### 수평선
-, *, _을 세개 이상 나열(`---`을 권장)

`--`

--

`---`

---

`***`
***

`___`
___




###테이블(실제로 자주 사용하지는 않음)
```markdown
first header | seconod header
------------ | ---------------
content form cell 1 | content form cell 2
content in the first column | content in the second column
```

| first header                | seconod header               |
| --------------------------- | ---------------------------- |
| content form cell 1         | content form cell 2          |
| content in the first column | content in the second column |



### 줄바꿈

키보드 엔터를 사용하면, 2줄바뀜이 되어있는 것처럼보입니다.

실제로 키보드 엔터의 기능은 `HTML`코드상으로 `<p>`의 기능을 처리하는 형태입니다. 문단의 구분역할을 합니다.
보이는 것 처럼 처리하려면 키보드 `shift`  + `enter` 처리하면 줄바꿈 처리됩니다.

보다 정확한 처리방법은 `<br>` 을 입력(`HTML`코드의 일부)하여 줄바꿈 처리하는 것이 정확한 처리로 구현됩니다.

---

## 마크다운의 장-단점

### 장점

```markdown
1. 간결하다.
2. 별도의 도구없이 작성가능하다.
3. 다양한 형태로 변환이 가능하다.
3. 텍스트(Text)로 저장되기 때문에 용량이 적어 보관이 용이하다.
4. 텍스트파일이기 때문에 버전관리시스템을 이용하여 변경이력을 관리할 수 있다.
5. 지원하는 프로그램과 플랫폼이 다양하다.
```

### 단점

```markdown
1. 표준이 없다.
2. 표준이 없기 때문에 도구에 따라서 변환방식이나 생성물이 다르다.
3. 모든 HTML 마크업을 대신하지 못한다.
```

---

기본적으로 'markdown' 은 별도의 디자인이 되는 기능이 아닙니다.
(불가능은 아니지만 기본 취지로는 다소 어렵다는 것 입니다.)
간단한 글을 빠르고 정확하게 표기하고 작성하는데 의미를 두고 사용합니다.

하지만 지금은 많은 테마/프레임 웍 등이 생겨나게 되면서 'markdown'
또한 다양하게 꾸미는 것이 가능하게 되었습니다.

<http://jjuliano.github.io/markdown-ui/>

<https://hexo.io>

<http://strapdownjs.com/>

위 페이지는 가장 대표적인 'markdown' framework 페이지 입니다.

참고하세요.

(단  jjulano.github.io 페이지의 경우는 루비를 기반으로 동작합니다.)

<https://rubyinstaller.org/>




