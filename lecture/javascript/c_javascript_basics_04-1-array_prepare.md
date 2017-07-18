# javascript 기초_4-1 array

지난시간까지 문법에대한 내용을 간단하게 진행하여 보았습니다.
실제 문서에서 사용하는 방법을 이해하려면 배열,객체,함수 등을 이해하고, 
DOM구조를 진행하면서 원하는 만큼 진행하실 수 있습니다.
이번시간에는 이전에 간단하게 배웠던 배열에대해 배워보도록 하겠습니다.

---

## 배열

**배열이란**? 여러내용을 나열하는 경우에 사용하는 것을 말한다고 알려드린 적이 있습니다.
좀더 정리하자면 다른 자바스크립트의 데이터 값을 하나의 목록으로 만드는 것을 배열 이라고 합니다.

---

[TOC]

---

### 배열을 사용하는 이유

우리가 웹에서 사용하는 기초 언어 3가지는 무엇인가요?
바로 **html**, **css**, **javascript** 입니다. 
우리는 이를 이렇게 작성합니다.

```javascript
웹구성1 = html
웹구성2 = css
웹구성3 = javascript
```

하지만 이를 작성하여 관리하기에는 생각보다 많은 부분을 차지하게 됩니다. 
그래서 우리는 아래처럼 정리할 수 있습니다.

```javascript
웹구성 = html,css,javascript
```

간편하면서도 정리하기 쉬운 형태입니다.

사실, 위 내용은 자바스크립트의 형태는 아닙니다. 
우리가 실제로 사용하는 형태의 내용으로 요약하는 그림입니다. 
하지만 위 내용과 동일한 형태로 자바스크립트의 구조로 처리할 수 있습니다 그것이 배열입니다.

```javascript
var web = ['html', 'css', 'javascript'];
```

위 내용은 배열의 형태로 변경처리하여 사용한 내용입니다. 
이전의 내용과 비교해 보았을 때 크게 달라지지는 않은 것을 알 수 있습니다.
다만, 배열은 여러개의 목록을 하나로 요약하는 형태이기 때문에 이를 그룹처럼 묶어주어야 합니다.
그룹의 형태로 만들어 내는 것을 `[ ]` 입니다.

다른 예시를 더 만들어 보겠습니다.

```javascript
var makePhoneCompany1 = 'samsung';
var makePhoneCompany2 = 'lg';
var makePhoneCompany3 = 'apple';
var makePhoneCompany4 = 'htc';
var makePhoneCompany5 = 'google';
var makePhoneCompany6 = 'nokia';
var makePhoneCompany7 = 'shaomi';

```

위 내용은 핸드폰 제조사에 대한 목록을 만드는 내용입니다.
실제로 존재하는 회사는 매우 많습니다.
모든 회사의 이름을 매번 변수로 지정하는 것은 사실상 무리가 있습니다. 이럴때 우리는 하나의 변수에 담아 사용합니다.

```javascript
var makePhoneCompany = ['samsung','lg','app;le', 'htc','google','nikia','shaomi'];
```

아주 간단하면서도 사용하기 쉬운 형태입니다.

그렇다면 변수의 값을 사용할때는 어떻게 처리할까요?

```javascript
var makePhoneCompany = ['samsung','lg','app;le', 'htc','google','nikia','shaomi'];
console.log(makePhoneCompany[0]);
```

위의 내용처럼 첫번째를 `0`으로 표기하고 이후 **1,2,3,4,5 ...**의 순서로 작성하면 원하는 결과를 얻어 낼 수 있습니다.

모든 목록을 모두 한번에 보고싶다면?

```javascript
for (var i=0; i<= makePhoneCompany.length; i++){
  console.log('핸드폰제조사' + i + ': ' + makePnoneCompany[i]);
}
```

이전에 배웠던 반복문을 사용하면 간단하게 모두 확인해 볼 수 있습니다.
위 내용에서 `makePhoneCompany.length`내용은 무엇일까요? 
변수 `makePhoneCompany`의 갯수를 파악하는 것입니다.

---

### 배열 만들기

배열을 만들때에는 각 괄호(대괄호) `[ ]`를 사용합니다. 빈 배열은 다음과 같이 한쌍의 각 괄호로 이루어져 있습니다.

```javascript
[];
```

즉, `[ ]`로 감싸져 있다면 이는 배열로 만들어져 있다고 생각하면됩니다.
이제 배열안에 내용을 담아 보겠습니다.
배열 안에 값을 넣으려면 괄호안에 값을 입력하되, 쉽표로 나눠주면 간단하게 해결됩니다.
배열 안에 들어간 개별값을 **원소(element)**라고 합니다.

```javascript
var graphicProgram = ['illustrator', 'photoshop', 'coreldraw', 'saitool','indesign','affinityDesign','affinityPhotoshop','autoCad','gimp'];
```

위 내용처럼 원하는 값(원소)를 작성하면 됩니다.
하지만 실제 가독성에는 다소 부족해 보입니다. 
결과가 같다면, 이왕이면 좀더 이쁘게 정렬해 놓는것이 나을것 같습니다.

```javascript
var graphicProgram = [
                  'illustrator', 
                  'photoshop', 
                  'coreldraw',
                  'saitool',
                  'indesign',
                  'affinityDesign',
                  'affinityPhotoshop',
                  'autoCad',
                  'gimp'
                ];
```

위 내용처럼 정리하여 작업한다고 하더라도 `;`기호가 나타나기전 까지는 한줄로 인지가 됩니다.
우리가 작업하는 내용을 가독성이 좋게 작업하는 것이 좋습니다.

---

### 배열 원소 설정 및 바꾸기

이제 각 괄호의 내용을 변수의 값에 정하고 작업할 수 있게되었습니다.
하지만 작업중 배열원소의 내용 중 일부를 수정하거나 변경처리해야 하는 경우가 발생할 수 있습니다.
이럴때는 어떻게 해야할 까요?

이전에 사용했던 변수 `graphicProgram`를 이용해 진해 보도록 하겠습니다.

```javascript
console.log('변경전: ' + graphicProgram[0]);
graphicProgram[0] = 'adobe Illustrator cc 2017';
console.log('변경후: ' + graphicProgram[0]);
```

위내용을 확인해보면 변수 `graphicProgram`의 첫 배열원소의 값은 **illustrator**입니다.
이후 첫배열원소의 값을 '**adobe Illustrator cc 2017**으로 변경처리하면, 변경된 값으로  처리가 되는 것을 알 수 있습니다.

만일, 위 내용에서 현재 9가지의 내용이 존재하는데, 실제 존재하지 않는 20번째의 값을 입력하면 어떻게 될까요?

```javascript
console.log(graphicProgram);
graphicProgram[19] = 'more graphic';
console.log(graphicProgram);
```

배열상에서 입력을 하지 않았더라도 이후의 값을 존재하게 만들려면 무언가 내용이 입력되어야합니다.
하지만 그 무언가의 값을 임으로 적용할 수는 없기 때문에 javascript는 이를 정의하지 않는 값으로 대처하게 만들어 버립니다.
즉 9번째 내용부터 18번째 까지의 값은 모두 `undefined`로 처리된다는 것 입니다.

---

### 배열에 원소 추가/제거

#### 원소추가

### 원소제거

---

### 배열 결합하기

---

### 배열에 여러자료형사용하기

#### 배열에 숫자, 문자 사용하기

#### 배열에 변수 사용하기

#### 이중배열 사용하기

---

### 배열원소 색인찾기

---

### 배열을 문자열로 만들기

---

### 배열 활용하기