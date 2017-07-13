# javascript 기초_4

지난시간에는 제어명령어중 분기와 관련된 `if`와 `switch`에 대해 알아보았습니다.

조건분기 처리와 동일하게 자주 이용되는 것이 **반복문**입니다.
반복문에는 `for`, `for~in`, `while`, `do~while`등 비슷하면서 다른 문법들이 존재합니다.
이번시간에는 각각의 반복문이 하는 기능과 내용에대해 이해해 보도록 하겠습니다.

---

 프로그램의 구조는 3가지로 구분이 가능합니다.

- 기술된 순서대로 처리를 행하는 **순차** 구조
- 조건에 따라 처리를 분기하는 **선택** 구조
- 특정의 처리를 반복 실행하는 **반복** 구조

---

[TOC]

---

### 반복

- while / do~while 
- for
- for~in
- forEach
- break/continue

---

#### while

```javascript
while(조건식){
  조건식이 true일 때에 실행되는 명령
}
```

---

#### do ~ while

```javascript
do{
  처음한번은 무조건 실행, 
  이후, 조건식이 true일때에 실행되는 명평
} while(조건식);
```

---

##### 무한루프

자바스크립트에서는 **무한루프**라는 것이 있습니다.
영원히 종료되지 않는(종료조건이 부합되지 않는 상태)루프를 말합니다.

---

#### for

조건식의 진위(true/false)에 대응하여 루프를 제어하는 반복문이 `while/do~while` 이라면,
미리 지정한 횟수만큼 반복처리를 행하는 명령이 `for` 문 입니다.

```javascript
for (초기화식; 루프 계속 조건식; 증감식){
  루프 내에서 실행하는 명령;
}
```

---

#### for ~ in

```javascript
for(가변수 in 배열/객체){
  루프 내에서 실행하는 명령;
}
```

```javascript
var member = ['에스프레소', '아메리카노', '아포가토'];
for (var i in memger){
  console.log('판매하는 커피는: '+ mamber[i]);
}
```

```javascript
var triangle = {width: 30, height: 50};
for (var j in triangle){
  console.log(j + '=' + triangle[j]);
}
```

```javascript
var book = new Object();
book.title = 'Javascript기초이해하기';
book.publish = '아무개출판';
book.price = '24,000';

for (var k in book){
  console.log(k + '는' + book[k]);
}
```



`for ~ in`루프문은 배열/객체 등의 기능을 간단하고 손쉽게 사용할 수 있다는 점에서 많은 분들이 사용하고 있으나,
실제로 배열의 내용을 `for ~ in`루프문으로 사용해서는 안됩니다.

- `for ~ in` 은 배열의 인덱스 번호를 취하기만 하므로 크다가 그다지 심플하게 되지 않습니다.
  (값에 대한 그 자체가 아니므로 오해를 불러일으킬 수 있습니다.)
- 코드에 따라 올바른 동작을 하지 않을 수 있습니다.
- 배열의 양이 많아질 경우 급격하게 느려지는 현상이 발생할 수 있습니다.
- `for ~ in`루프문을 사용하는 것은 연상배열(해시), 객체의 키를 조회하는 경우에 한하며, 
  일반 배열을 조회시 원칙적으로 for문을 이용하는 것이 좋습니다.

---

#### break/continue(루프 도중 Skip / 중단하기)

일반적으로 반복문의 명령인  `for`, `for~in`, `while`, `do~while`등은 
미리 정해진 종료 조건을 만족하는 타이밍에 루프를 종료합니다.

하지만, 특정 조건을 만족하는 경우에 루프를 강제적으로 중단하고 싶은 경우도 있습니다.
그러한 경우에 이용할 수 있는 것이 `break`([switch 참조](c_javascript_basics_03_1.md))입니다.

```javascript
var result = 0;
for (var i = 0; i<= 100; i++){
  result += i;
  if(result > 1000){break;}
}
console.log('합계 값이 1000을 넘는 것은' + i);
```

```javascript
var result = 0;
for(var i = 0; i<100; i++){
  if( i % 2 == 0 ){continue;}
  result += i;
}
console.log('합계: ' + result);
```

---

##### 중첩된 루프를 한번에 빠져나오기(레이블 구문)

중첩된 루프안에서 `break/continue` 명령을 사용한 경우
`default`로 가장 안쪽의 루프를 빠져 나오게 됩니다.

```javascript
for(var i = 1; i< 10; i++){
  for(var j = 1; j<10; j++){
    var k = i * j;
    if(k > 30){break;}
    console.log(k + '-');
  }
  console.log('<br />');
}
```

여기서 변수 `k`가 30이 넘는 경우에 `break` 명령을 실행하고, 있습니다.
이로인해 안쪽 루프(내부에 존재하는 for문)을 빠져 나오고 있으므로, 결과적으로 
**곱셈값이 30이하인 값만을 표시하는 구구단**이 생성되게 됩니다.

이것을 곱셈값이 30을 넘으면 구구단 출력 자체를 정지시키도록 만들고 싶다면, 아래의 내용을 참고하시면 됩니다.

```javascript
kuku:
for(var i=1; i<10; i++){
  for(var j = 1; j<10; j++){
    var k = i * j;
    if(k>30){break kuku;}
    concole.log(k + '&nbsp');
  }
  console.log('<br />');
}
```

