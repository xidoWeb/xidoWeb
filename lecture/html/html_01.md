# web

------

## html

> h, p, span, a, img, div, br, table, ul, ol, li, dl, dt, dd, td, th, tr, input, form, select, button, fieldset, legend,

> target, submit, reset, src, href, class, id, .........

------

1. h1 ~ h6 (제목:h1제일중요 , 1번사용 가능)

2. p (문단)

3. br (줄바꿈)

4. hr (라인:영역나누기/ 화제의 전환)

5. span (의미없는 영역/ 인라인태그)

6. a (앵커태그/ 링크 ) : href="링크" target="_blank | _self"

7. img (이미지) : src="이미지" alt="이미지 설명"

8. div (그룹)

9. list(ul, ol, dl)

   - ul (순서 x)
     - li
   - ol (순서 o)
     - li
   - dl (데이터 제목/내용)
     - dt
     - dd

10. table (표) :summary="상세 설명"

    - caption(표제목)
    - tr(행)
    - th(셀제목)
      -  colspan | rowspan  (셀병합)
    - td(셀내용)
      -  colspan | rowspan  (셀병합)
    - thead (tr의 내용중 제목영역에 속하는 부분을 묶어 놓은부분)
    - tbody (tr의 내용중 내용영역에 속하는 부분을 묶어 놓은부분)
    - tfoot (tr의 내용중 결과에 속하는 부분을 묶어 놓은부분)
    - 속성: scope, row, col

11. form(입출력가능한 기능): action="" method="get | post"

    - `fieldset` (form내부 영역)
      - `legend` (form 영역별 제목)
    - `input` : **type**(형태) , **name**(서버와 연동 이름) , **id**(+label for연동), **value**(값)
      - **text**: maxlength="10"
      - **password**: maxlength="10"
      - **radio**: checkd="checked"
      - **checkbox**: checkd="checked"
      - **submit**
      - **reset**
      - **button**
      - **file**
      - **image**: src, alt
    - `textarea`: name id cols rows readonly="readonly"
    - `select`: name id
      - `optgroup`: label
      - `option`: value
    - `button`: type="submit | reset | button"
    - `label`: for (input의 id와 연결)
    - `<!-- -->`

    ------