# javascript 기초_1

이전 시간에는 자바스크립트를 사용하면서 가장 중요한 변수에 대해 알아 봤습니다.
무언가 복잡하고 어려운것 일 수도 있지만 간단하게 설명하면,
변수는 어떠한 값을 담아두기 위한 약속된 이름으로 기억하면 쉽게 다가갈 수 있습니다.

이번 시간에는 변수를 사용하여 표현하는 다양한 계산식과, 표현들을 익혀
 변수와 자바스크립트에 대한 부분을 좀더 친숙하게 다가가 보도록 하겠습니다.

---

[TOC]

---

## 변수의 이해

### 기초개념

```javascript
var old;
```

위는 변수를 선언한 내용입니다.
무엇도 대입하지 않았으므로 검증시 값은 `undefined` 라고  표기됩니다.

```javascript
old = 24;
```

처음 선언되어진 변수 `nickName`에 리터럴값인 24로 표기하였습니다.
old의 값은 **24**로 변경됩니다.
이전에 배웠던 내용을 간단하게 확인하는 내용이었습니다.

---

### 계산하며 변수 생성하기

변수를 활용하여 계산식을 만들고, 그결과를 새로운 변수에 저장하는 방법을 익혀 보겠습니다.

```javascript
var minute = 60;
var hour = 60;
var hourSecond = minute * hour;
console.log(hourSecond);
```

위의 내용은 한시간은 몇 초인지를 계산하기 위해 만들어진 식입니다.
1분은 60초로 나눠져있고, 1시간은 60분으로 변수값에 설정 하였습니다.
이를 기반으로 1시간은 몇초인지를 구하라는 식을 해결하기 위한 식을 처리한 것입니다.

이제 하루를 몇초로 나뉘어지는지, 일년은 몇초로 구성되어지는지 계산하는 식을 만들어 보겠습니다.

```javascript
var day = 24;
var year = 365;

var daySecond;				// 하루는 몇초인지 확인
var yearSecond; 			// 일년은 몇초인지 확인
```

우선 하루는 몇시간인지, 1년은 몇일인지를 변수에 저장하고 그에따른 값을 도출 시키도록 하겠습니다.

```javascript
var daySecond = hourSecond * day;
var yearSecond = hourSecond * day;
```

이제 좀더 진행해 보겠습니다. 
여러분의 나이는 약 몇초가 지났을까요?(년수로만 계산해 보겠습니다.)

```javascript
var myYearsOld = 35;
var myYearsSecond = yearSecond * myYearsOld;
```

---

### 증가와 감소

숫자가 포함된 값을 1씩 늘리거나 줄여되는 때가 있습니다. 
1분이 지날때 마다 1씩 늘어나기도하고, 시험날짜를 셀때 하루씩 빼기도 합니다.
이렇게 1씩 늘어나는것을 증가(increment), 1씩 줄어드는 것은 감소(ddcrese)라고 부릅니다.

1씩 늘어나는 증가는 `++`라는 연산자를 사용하며, 1씩 감소 하는 연산자는 `--`라고 합니다.

```javascript
var minuteTime = 30;
++minuteTime;
console.log(minuteTime);
++minuteTime;
console.log(minuteTime);
++minuteTime;
console.log(minuteTime);
++minuteTime;
console.log(minuteTime);

var myEgg = 30;
--myEgg;
console.log(myEgg);
--myEgg;
console.log(myEgg);
--myEgg;
console.log(myEgg);
```



---

### 더하기, 빼기

변수의 값을 일정한 수에 따라 늘리고 싶을 때가 있습니다.
또는 일정한 값을 빼야 할때도 있습니다. 

```javascript
var applePrice = 500;
applePrice = applePrice + 300;
console.log(applePrice);

applePrice = applePrice - 200;
console.log(appldePrice);
```

위 내용은 사과의 가격이 최초에 500원이었는데, 가격이 올라 800원으로 늘어난 것입니다. 
시간이 지나면서 사과의 가격이 200원이 내려 600원으로 줄어드는 것으로 표현한 내용입니다.

우리는 위 내용을 보면서 조금 의문이 듭니다.
`applePrice`는 자기 자신의 금액을 늘리거나 줄어드는 경우로 표현되고 있습니다.

좀더 쉽게 처리하는 방법은 없는지 확인해 볼 필요가 있지 않을까요?

```javascript
var grapePrice = 3000;
grapePrice += 1000;
console.log(grapePrice);

grapePrice -= 1500;
console.log(graphPrice);
```

위 식은 같은 내용을 좀더 간단한 식으로 조정한 내용입니다.
변수 `grapePrice`를 생성해 포도의 기본가격을 3000원으로 책정한 다음, 시간이 지나 1000원을 더 올리는 내용입니다.
이때 들어있는 연산자의 기호를 보면 `grapePrice` `+=` 라는 내용을 확인 할 수 있는데, 자시 자신에게 라는 뜻으로 분석할 수 있습니다.

즉, 포도가격 자체를 변동하기 위해서는 `+=`라는 연산자를 사용하면, `grapePrice = grapePrice + 1000`의 공식을 사용하지 않아도 문제없이 작성 할 수 있다는 것입니다.
바로 아래의 내용인 `-=` 또한 마찬가지 내용입니다. 
`grapePrice`의 가격을 1500원 낮춘다는 의미로 사용할 수 있습니다.

이전에 보았던 `++`.`-—`와 마찬가지로 자주 사용하는 연산의 기능입니다.
간단하게 보는 내용이지만 잘 익혀두어 이후에 배우는 연산자들과 함께 사용하세요.

---

### 문자열

이번에는 숫자가 아닌 문자를 사용해 보도록 하겠습니다.

변수의 경우는 숫자를 문자로 변환하거나 문자를 숫자로 내용을 바꾼다고해서 문제가 되지 않습니다.

```javascript
var myKey = 10;
myKey = 'martiz';
```

`myKey`변수가 처음에는 10 이었다가, 새로운 값인 'martiz'로 변경하여, 현재의 변수 `myKey`는 'martiz'라는 값으로 변동된 것 입니다.

또는 문자 '100'을 숫자 100으로 전환 하기도 합니다.

```javascript
var myNum = '100';
var encoding = parseInt(myNum);
console.log(encoding);
```

`myNum`은 문자 100입니다.

이는 값이 문자 100으로 표현되어 있지만 숫자로도 전환이 가능한 코드입니다.
그래서 `parseInt()`라는 추가 명령어를 첨부하였습니다.

결과는 숫자 100으로 변형됩니다.
간단하게 보자면 `parseInt()`는 정수로 전환하라는 명령어 입니다.
'( )'안에 필요한 값을 넣으면 숫자료 전환가능한 내용은 정수형 숫자로 변합니다.
단, 문자 중간에 숫자가 온다면 처리 되지 않습니다.

> 어떠한 명령어중에 `()`를 동반하는 명령어는 메소드 라고 합니다. 어떠한 기능을 실행하게 하는 기능이라고 보시면 됩니다.간단한 예로 `console.log()`를 보면 `log()` 부분이 `parseInt()`형태와 동일하게 되어져 있습니다.
> 결국 `log()`기능도 실행을 하는 명령어인 메소드 라고 보면 됩니다.



```javascript
var myText = '1myText10000';
var encoding = parseInt(mtText);
console.log(encoding);
```

첫글자가 숫자 형태로 되어 있어야하며, 한글자라도 문자가 들어있다면 그 이후의 내용은 모두 사라지게 됩니다.

```javascript
var nine = 9;
var textNine = '9';
console.log(nine + textNine);
```

위 코드는 숫자 9와 문자 9를 더하는 내용입니다.
`parseInt()`기능을 사용하지 않은 상태입니다.

결과는 무엇이 나올까요? `99`입니다.
자바스크립트는 문자와 숫자를 더하면 있는 그대를 나열하게 되는 현상이 발생하게 됩니다.

어떤 문자형태가 오든 숫자 또는 또다른 문자를 더하게 된다면, 결과는 위 코드와 동일하게 나열되는 현상으로 처리되게 됩니다.

```javascript
var name = 'xido';
var web = 'WebPage';
var xidoWeb = name + web;
console.log(xidoweb);
```

위 내용을 작성하고 내용을 파악해 보세요.

---

### 문자열 연결하기

위 코드에서 확인했든 `문자 + 문자`, `문자 + 숫자`, `숫자 + 문자`의 경우는 나열의 형태를 지니게 됩니다.

```javascript
var green = 'green ';				// 띄어쓰기 확인
var com = 'computer';
var comColl = green + com;
console.log(comColl);
```

위코드는 한번 더 체크해 보기 위한 코드 내용입니다.
단지 조금 다른점이 있다면 `green`코드 내부에는 띄어쓰기를 사용했다는 것 입니다.
이로인해 실제로 보여주는 코드 또한 단어와 단어 사이가 띄어져 있습니다.
`HTML`와 유사한 내용으로 내용중의 일부는 떨어뜨릴 수 있습니다.

---

### 문자열 길이 구하기

문자열의 길이를 구하는 방법은 문자열 끝에 `.length`만 더하면 됩니다.

```javascript
'자바스크립트를쉽게이해하기'.length;
```

위 내용을 브라우저에서 직접 작성하여 확인해보면 13이라는 값이 나오게 됩니다.
물론 직접 확인하는 것 보다는 변수를 사용하여 처리하는 것이 좀더 정확하고 깔끔한 표현입니다.

```javascript
var myjs = 'javascript'.length;
var learn = '쉽게이해하기';
console.log(myjs + learn.length);
```

위 내용에서 `.length`는 `()`를 붙이지 않습니다.
`()`를 붙이는 것은 어떠한 실행을 의미하는 메소드를 의미하는 것이고,
위 코드는 무언가를 변환시키거나 새롭게 적용하는 등의 실행의 효과가 아닌 확인의 코드일 뿐입니다.

```javascript
var java = 'java';
var script = ' script';
var webLang = java + script;
console.log(webLang.length);
```



---

### 문자열에서 한글자 가져오기

문자열에서 한글자만 가져와서 처리하는 경우도 있습니다.
목록에 있는 글자 일부를 조합했을때 암호를 만들어 사용할 수도 있습니다.

```javascript
var secret1 = '자바스크립트를 이해하기';
var secret2 = '병역 신체검사';
var secret3 = '잘만든 작품을 보면 나오는 감탄사!';
var secretTextResult = secret1[0] + secret2[3] + secret3[16];
console.log(secretTextResult);
```

위내용에서 `[ ]` 기호의 경우는 틍정위치의 순서를 나타내는 표현입니다.

즉, `secret1`의 첫번째는 `[0]`을 입력하게 되어있습니다. 처음은 0으로 시작한다는 기호 표기를 잘 이해해야 위 내용을 쉽게 이해 할 수 있습니다.

---

### 문자열 잘라내기

```javascript
'문자내용 잘라내기'.slice(1,5);				// 문자 '문자내용 잘라내기'의 두번째 글자에서 여섯번째 글자 까지
```

위 내용은 어떠한 글자를 사용하는데 있어 일부 텍스트를 잘라내고, 필요한 텍스트를 사용하도록 처리하는 내용입니다.

```javascript
var longText = '긴 문자열의 내용을 잘라내기';
```





---

### 문자열 대/소문자 바꾸기

```javascript
'hello my javascript studing team'.toUpperCase();

'hello my javascript studing leader'.toLowerCase();
```



