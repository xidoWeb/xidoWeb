# WebStandard
> 하이퍼텍스트 마크업 언어(HTML)는 웹페이지를 만들고 보여주는데 사용됩니다. 웹 페이지의 컨텐츠를 결정짓지만, 기능을 결정하지는 않습니다.

> HTML로 글에 "마크업"을 추가할 수 있습니다. "하이퍼 텍스트"는 오늘날의 월드 와이드 웹을 특징지우는 웹페이지를 서로 연결하는 것을 의미합니다. 인터넷에 웹페이지를 만들고 올려서 월드 와이드 웹의 참여자가 될 수 있습니다. HTML은 시각적인 이미지와 다른 형태의 미디어도 지원합니다. HTML은 웹 문서의 구조와 의미를 기술하는 언어입니다. 웹 페이지의 내용은 `<img>, <title>, <p>, <div>, <picture>` 등의 HTML 요소로 표시됩니다. 이 요소들은 웹사이트를 구성하는 기초 재료입니다.

[MDN 웹표준](https://developer.mozilla.org/ko/docs/Web/HTML)
[DAUM 웹표준](http://darum.daum.net/convention/html)

___
## 웹표준의 기본 내용 
___
1. 접근성
'모든 사용자가 신체적, 환경적 조건에 관계없이 웹에 접근하여 이용할 수 있도록 보장하는 것'을 의미한다. 마우스가 없는 환경이나 키보드만을 조작해야 할 경우, 신체적 장애로 인해 특수한 환경하에 접속해야 되는 경우, 브라우저별, 모바일 환경에서 접속해야 되는 경우와 같이 다양한 플랫폼에서도 정보제공에 다름이 없어야 한다.

___
우리나라 대부분의 사이트는 Internet explorer 환경에만 최적화 되어 있으며, ActiveX, Flash, Image의 과도한 사용과 웹표준을 준수하지 않은 코딩 등으로 다양한 기술적 환경을 지원하지 못하고 있으며, 신체적 제한조건을 가진 고령자나 장애인 등이 이용 하기에 불편한 부분이 많다. 웹접근성을 준수한 사이트는 기술적 환경이나 신체적 조건에 관계없이 웹 콘텐츠를 이용할 수 있도록 해 준다.

___
**웹접근성은 법적으로 강제할 수 있다.** 이는 장애인 차별 금지법에 근거하여 그 효력을 발휘합니다. 사이트를 제작시 상업적인, 혹은 공적인 사이트를 제작하게 된다면 이를 염두에 두어야 합니다. 차후에 수정할때 금전적, 시간적 낭비를 줄이기 위해서라도 처음부터 웹접근성에 입각하여 제작하길 바랍니다.

___
2. 구조와 표현의 분리
웹 표준을 준수함으로써 웹 문서 파일의 용량을 줄일 수 있고 이로 인한 트래픽 감소 효과를 얻을 수 있다. 이는 물리적인 서버용량의 증가를 막을수 있기 때문에 경제적인 효과를 얻을 수 있다.

___
단편적인 예로, 웹 표준을 준수하는 사이트는 구조와 표현을 분리해서 개발하기 때문에 사이트의 용량이 기존에 비해서 현저히 적어진다. CSS는 HTML과 구조가 분리되어 있기 때문에 한 번 해당 페이지를 불러오게 되면, 브라우저의 캐시에 CSS가 저장되고 메모리에 상주하게 되어 동일한 CSS는 다시 불러오지 않아 HTML 코드가 가벼워지게 되는 것이다.

※ HTML을 캐시하지 않는 이유

 -  HTML은 정적이지 않으므로  javascript와 같은 동적인 기능을 구현할때 그 구조가 자주 변한다.

___
3. 사이트 개발및 유지 보수
구조와 표현을 분리하기 때문에 사이트 개발시에 코딩 & 디자인 & 프로그래밍이 동시에 진행될 수 있기 때문에 개발 기간이 많이 단축되며, 웹페이지가 단순화되어 디버깅에 유리하다. 또한, 손쉽게 디자인만을 변경하여 리뉴얼 시킬 수 있어 유지 보수에 용이하다.


___
4. 검색 친화적인 웹 사이트 구현
meta 요소를 이용한 정확한 문서 정보의 제공과 적절한 제목(heading 요소)의 사용, 의미에 맞는 마크업은 검색 시 결과에 영향을 미칠 수 있는 중요한 정보이다. 따로 홍보를 위한 비용을 지출하지 않더라도 충실하게 작성된 문서 정보만으로도 검색의 효율성을 높일 수 있다.

___
5. 호환성의 확보
표준 웹 기술을 사용하게 되면, 기종 혹은 플랫폼에 따라 달리 보이거나 혹은 의도된 바와는 전혀 다른 모습의 사이트가 보이게끔 하는 것을 방지할 수 있다.


___
물론, 국내의 브라우저 이용현황이 웹표준 준수에 미약한 IE 점유율이 높기 때문에 모던 브라우저들(크롬, 사파리, 파이어폭스, 오페라)을 위한 웹표준으로 웹문서를 작성한 후 IE를 위한 작업을 따로 해야 하는 경우가 많은 것이 사실이다. 외국에서는 IE를 Stupid Browser라 칭하며 그 사용을 꺼려하고 있으며 혹시나 아직도 IE8 이하의 브라우저들을 사용하고 있다면 모던 브라우저들로 바꾸어 보는 걸 추천한다.



출처: http://webdir.tistory.com/34 [WEBDIR]

___
## 웹 버전
1. html  
    * html 4.0.1
```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html lang="en">
<head>
	<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
	<title>Document</title>
</head>
<body>
	
</body>
</html>

```

___

  * xthml 1.0  
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">
<head>
	<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
	<title>Document</title>
</head>
<body>
	
</body>
</html>
```
___
  * html 5
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	
</body>
</html>
```
___
  * html 5.1
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	
</body>
</html>
```
___
2. css
    * css2
    * css3

___
## HTML5의 개념 및 특징

차세대 웹 표준으로 확정(2014년 10월 28일)되었으며, 기존 텍스트와 하이퍼링크만 표시하던 HTML이 멀티미디어 등 다양한 애플리케이션까지 표현·제공하도록 진화한 “웹 프로그래밍 언어“입니다. 예로, 오디오·비디오·그래픽 처리, 위치정보 제공 등 다양한 기능을 제공함으로써, 웹 자체에서 처리할 수 있는 기능이 대폭 향상 되었습니다.
___
### html [^1]
  * 기본 영역
  * 링크 &amp; 이미지
  * 이름지정하기
  * 외부 문서 불러오기
  * 테이블
  * 폼
  * 블록구조화(시멘틱하게)
  * video & audio
  * 조건부 주석
<!-- 
___
## 
___
### svg
___
### canvas
-->
___
## css3의 개념 및 특징

CSS3는 Cascading Style Sheets(CSS) 언어의 가장 최신 버전이고 CSS2.1을 상속하는 것을 목표로  합니다.  CSS3는 개발자들이 오랫동안 기다려온 새로운 기능들을 지원하게 되었습니다. 다중열(multi-columns), 유동적인 상자(flexible box), 격자 배치(grid layouts) 뿐만 아니라 둥그런 모서리(rounded corners), 그림자( shadows) , 부드러운 색의 변이(gradients) , 변이(transitions), 움직임(animations) 등도 지원합니다. 실험적인 부분(experimental parts)은 브라우저 공급자(vender)의 구현에 따라 다를 수 있고 미래에 문법이나 의미가 변할 수 있습니다. 따라서 환경에 따라 해당 스펙을 사용하는 것을 피하거나, 사용하더라도 매우 신중히 사용해야합니다.  
___
> 2002년 8월부터 2011년 6월까지 CSS Level2가 권장(Recommendation)단계에 이르기 까지 총 9년이 걸렸습니다. 이는 몇몇 부차적인 기능들이 전체 명세(specification)의 진행을 더디게 만들었기 때문입니다. W3C의 CSS Working Group은 문제를 일으키는 몇몇 기능을 제외한 나머지 기능들의 표준화 작업을 보다 빠르게 진행하기 위하여 Beijing doctrine에 따라 CSS를 보다 작은 컴포넌트 단위로 나눴고, 이를 모듈(module)이라 부릅니다. 현재 각각의 모듈은 서로 독립적으로 표준화 과정을 거치고 있습니다. 이미 몇몇 모듈은 W3C Rocommendations 에 이르렀으나, 나머지는 여진히 Working Drafts 단계에 머물러 있습니다. 또한 새로운 요구사항(needs)이 발생할 때 마다 계속해서 새로운 모듈이 추가되고 있습니다.
___
> CSS Modules and Snapshots as defined since CSS3공식적으로 CSS3 자체 표준은 존재하지 않습니다. 각각의 모듈이 독립적으로 표준화 되고 있고, 표준 CSS는 모듈을 통해 CSS2.1을 수정하여 상속(extends)하는 것으로 구성되어있서 항상 같은 level number를 갖는 것은 아닙니다. 특정 시점의 CSS2.1과 완성된 모듈들로 구성된 CSS표준 스냅샷을 정의할 수 있습니다. W3C는 주기적으로 이런 스냅샷을 발표하고 있습니다. (2007 / 2010)

___
### css [^2]
  * 선택자
  * size &amp; unit
  * background
  * display
  * float & clear
  * margin &amp; padding &amp; border &amp; outline
  * position
  * font
  * prefix
  * border-radius
  * transform
  * transition
  * animation
___



[^1]: html.md
[^2]: css.md
