# javascript 기초_2

이전시간에는 변수의 값을 이용한 간단하고 다양한 내용을 익혀보았습니다.
이번시간에는 좀더 깊이있고 복잡하지만 꼭 알아야하는 기본 연산자에 대한 부분을 알아 보도록 하겠습니다.

---

[TOC]

---

## 연산자

자바스크립트는 다양한 연산자를 가지고 있습니다.

**연산자(Operator)**란, 부여된 변수/리터럴에 대하여 미리 결정된 어떠한 처리를 행하기 위한 기호입니다.
예를 들자면 `=`, `,`,`-`,`+` 등이 모두 연산자 라고 부릅니다. 
이때, 연산자에 의해 처리되는 [변수](b_javascript_beginners_04.md)/[리터럴](b_javascript_beginners_03.md)을 **오퍼랜드(Operand-피연산자)**라고 불립니다.

![operator](./img/operator.png)

---

## 연산자 종류

- 산술연산자
  - 사칙연산
  - 증감연산자
- 대입연산자
- 문자열 연산자
- 비교연산자
  - 등가연산자
  - 동치연산자
  - 조건연산자
  - 논리연산자
- 비트연산자
- 반대연산자
- 기타연산자


---

### 산술연산자

산술연산자는 대수 연산자라고도 하며, 표준적 사칙연산을 시작으로 수치와 관련된 연산을 행하는 것을 말합니다.

아래는 산술연산자의 연산 기호를 간단하게 표로 표현한 내용입니다.

| 연산자  |          개요          |         예시         | 예시결과      |
| :--: | :------------------: | :----------------: | --------- |
|  +   | 숫자의 덧셈(문자의경우 나열을 의미) |       3 + 5        | 8         |
|  -   |        숫자의 뺄셈        |       10 - 7       | 3         |
|  *   |        숫자의 곱셈        |       3 * 5        | 15        |
|  /   |       숫자의 나눗셈        |       10 / 5       | 2         |
|  %   | 숫자의 나머지연산(나누고 남은 값)  |       10 % 4       | 2         |
|  ++  |  전위/후위형 덧셈(1씩 더하기)   | x = 3; x++ \|  ++x | 3(4) \| 4 |
|  --  |   전위/후위형 뺄셈(1씩 빼기)   | y = 3; y-- \| --x  | 3(2) \| 3 |

---

#### 사칙연산자

**+** (더하기), **-** (빼기), ***** (곱하기), **/** (나누기), **%** (나머지)     

우리가 익히 알고 있는 **더하기, 빼기, 곱하기, 나누기**식을 포함한 것을 의미하며, 
여기에 **나머지**라는 하나의 연산을 추가합니다.

```javascript
var result;							// 변수 'result' 선언
result = 20 + 3;  					// 변수 'result' 계산값 부여(더하기)
console.log("값: ", result);  		// 변수 'result' 값 확인하기
result = 20 - 3;  					// 변수 'result' 계산값 부여(빼기)
console.log("값: ", result);  
result = 20 * 3;  					// 변수 'result' 계산값 부여(곱하기)
console.log("값: ", result);  
result = 20 / 3;  					// 변수 'result' 계산값 부여(나누기)- 정수로 변환시 parseInt()
console.log("값: ", result);  
result = 20 % 3;  					// 변수 'result' 계산값 부여(20에서 10을 나눈뒤 나머지값)
console.log("값: ", result);  
```

---

#### 문자열 연산자

기본적으로 사칙연산자와 크게 다르지 않습니다. 
다만 문자열 연산자는 **문자 + 문자**, **문자 + 숫자** 형태의 기능을 의미합니다. 

```javascript
var my = 'my';
var lang = ' language is Korean';

console.log(=my + lang); // console logs the string "my language is Korean".
```

---

#### 증감연산자

전위형 덧셈/뺄셈 , 후위형 덧셈/뺄셈으로 자기 자신에게 **1씩 더하거나, 1씩 뺄때** 주로 사용합니다.
작업과 동시에 값을 확인하는 경우,
**전위형**의 경우는 연산을 한 값을 도출하며, 
**후위형**의 경우는 값도출 후 연산한다는 차이를 볼 수 있습니다.

##### 전위형 덧셈

```javascript
var before = 0;
// 연산 후 확인
console.log('최초: ', before);
++before;
console.log('처음1더하기: ', before);
++before;
console.log('두번째1더하기: ', before);
//연산 자체를 확인
console.log('현재값: ', before);
console.log('바로1더하기:', ++before);
console.log('두번째 바로 1더하기:', ++before);
console.log('세번째 바로 1더하기:', ++before);
console.log('네번째 바로 1더하기:', ++before);
console.log('다섯번째 바로 1더하기:', ++before);
```



##### 후위형 덧셈

```javascript
var after = 20;
// 연산 후 확인
console.log('최초: ', after);
after++;
console.log('처음1더하기: ', after);
before++;
console.log('두번째1더하기: ', after);
//연산 자체를 확인
console.log('현재값: ', after);
console.log('바로1더하기: ', after++);
console.log('두번째 바로 1더하기:', after++);
console.log('세번째 바로 1더하기:', after++);
console.log('중간 확인하기:', after);
console.log('다시 바로 1더하기:', after++);
console.log('다시 두번째 바로 1더하기:', after++);
console.log('값 재확인:', after);
```



##### 전위형 뺄셈

```javascript
var before = 20;
// 연산 후 확인
console.log('최초: ', before);
--before;
console.log('처음1빼기: ', before);
--before;
console.log('두번째1빼기: ', before);
//연산 자체를 확인
console.log('현재값: ', before);
console.log('바로1빼기:', ++before);
console.log('두번째 바로 1빼기:', --before);
console.log('세번째 바로 1빼기:', --before);
console.log('네번째 바로 1빼기:', --before);
console.log('다섯번째 바로 1빼기:', --before);
```



##### 후위형 뺄셈

```javascript
var after = 0;
// 연산 후 확인
console.log('최초: ', before);
before--;
console.log('처음1빼기: ', before);
before--;
console.log('두번째1빼기: ', before);
//연산 자체를 확인
console.log('현재값: ', before);
console.log('결과도출 후1빼기: ', before--);
console.log('두번째 결과도출 후 1빼기:', before--);
console.log('세번째 결과도출 후 1빼기:', before--);
console.log('중간 확인하기:', before);
console.log('다시 결과도출 후 1빼기:', before--);
console.log('다시 두번째 결과도출 후 1빼기:', before--);
console.log('값 재확인:', before);
```



---

### 복합 대입 연산자

대입연산자란 지정된 변수에 값을  대입하는 연산자를 말합니다.
앞서 보던 `=`의 표기는 대입연산자의 일종입니다.

| 연산자  | 개요 (좌변값에 우변값을 대입하는 기능)                 | 예시               | 예시결과   | 뜻           |
| ---- | -------------------------------------- | ---------------- | ------ | ----------- |
| =    | 변수 등에 값을 대입한다.                         | x = 1            |        | x = 1       |
| +=   | 우변 값을 더한 값을 대입한다.                      | x = 3; x += 2    | // 5   | x = x + 2   |
| -=   | 우변 값을 뺀 값을 대입한다.                       | x = 3; x -= 2    | // 1   | x = x - 2   |
| *=   | 우변 값을 곱한 값을 대입한다.                      | x = 3; x *= 2    | // 6   | x = x * 2   |
| /=   | 우변 값을 나눈 값을 대입한다.                      | x = 3; x /= 2    | // 1.5 | x = x / 2   |
| %=   | 우변 값을 나눈 나머지 값을 대입한다.                  | x = 3; x %= 2    | // 1   | x = x % 2   |
| &=   | 우변 값을 비트 AND 연산한 값(논리곱)을 대입한다.         | x = 10; x &= 5   | // 0   | x = x & 5   |
| \|=  | 우변 값을 비트 OR 연산한 값(논리합)을 대입한다.          | x = 10; x \|= 5  | // 15  | x = x \| 5  |
| ^=   | 우변 값을 비트 XOR 연산한 값(배타논리합)을 대입한다.       | x = 10; x ^= 5   | // 15  | x = x ^ 5   |
| <<=  | 우변 값만큼 좌측 쉬프트(이동)한 결과를 대입한다.           | x = 10; x <<= 2  | // 20  | x = x << 2  |
| >>=  | 우변 값만큼 우측 쉬프트(이동)한 결과를 대입한다.           | x = 10; x >>=1   | // 5   | x = x >> 2  |
| >>>= | 우변 값만큼 우측 쉬프트한 결과를 대입한다. ([^Unsigned]) | x = 10; x >>>= 2 | // 2   | x = x >>> 2 |

\[^Unsigned]: 절대값

---

#### 대입연산자 1: ( = )

자바스크립트의 연산자중 가장 많이 접하는 연산자는 대입연산자 입니다. 
그중에서 가장 으뜸은 `=`기호입니다.

```javascript
// 기본 전달방식(기본형)
var x = 1;
var y = x;
x = 2;
console.log(y);

// 참조 전달방식(참조형)
var ary1 = [0,1,2];
var ary2 = ary1;
ary1[0] = 5;
console.log(ary2);
```

자바스크립트의 데이터 형에는 크게 기본형과, 참조형으로 구분이 가능합니다.
이때 위의 예시를 보면 하나는 기본형의 예시를, 또다른 하나는 참조형의 예시를 보여준 예입니다.



##### 기본형

기본형의 값은 변수에 직접 보관되는 값으로 변수 `x`의 값을 `y`에 인도할 경우 그 값이 복사 되도록 한 것입니다.
이를 값에의한 전달 이라고 합니다.

위의 예시의 설명을 보자면 변수`x`에 1을 대입하고 `y`에 `x`를 다시 대입한 경우입니다.
이럴 경우 `y`에는 1이라는 값이 대입되게됩니다. 
이후 `x`의 값을 2로 변경처리하며, 이때 `y`는 2로 변경되지 않습니다.

이 대입방식은 `x`의 값을 복사한 값으로 처리된 것이기 때문에, 이후의 `x`의 값을 변경해도 `y`는 영향을 받지 않습니다.



##### 참조형

기본형의 내용에 비해 참조형의 경우는 좀 복잡합니다.
배열 리터럴을 변수 `ary1`에 담고, 이를 다시 변수 `ary2`에 대입하고 있습니다. 
이때, 참조형의 경우에는 값 자체를 담는 것이아닌 보관의 어드레스만 변수에 보관됩니다.

즉, `ary2 = ary1` 내용은 변수 `ary1`에 보관되어 있는 주소를 변수 `ary2`에 보관하고 있는 것입니다.

이러한 값의 전달방식을 **참조전달**이라고 합니다.
즉, 이시점에서 `ary1`과 `ary2`는 쌍방이 모두 같은 값을 보고 있게 되는 것이기에, 
`ary1`의 변경은  `ary2`에도 영향을 미친다는 뜻입니다.

- **값 전달**: 값 그자체를 건네주는것
- **참조 전달**: 값을 보관하고 있는 참조 장소의 정보를 건네주는 것

---

#### 구조해제/비구조화 할당(destructuring assignment)

복잡한 대입 연산에서, [구조 해제 대입](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) 문법은 배열의 구조나 객체를 반영하여, 
배열이나 객체에서 데이터를 추출할 수 있게 해주는 자바스크립트 표현입니다.

이름이 하나로 정해져 있는 게 아니라서 구조분해라고 하는 사람도 있고, 
**비구조화**라는 사람도 있고 **객체 파괴**라는 사람도 있습니다.
**비구조화 할당**(**destructuring assignment**) 구문은 배열 또는 객체에서 데이터를 
별개(distinct) 변수로 추출할 수 있게 하는 JavaScript 식(expression:표현)입니다.

구조해제 대입문법은 ES6이후의 내용에서 좀더 다뤄보겠습니다.

```javascript
var foo = ["one", "two", "three"];

// without destructuring
var one   = foo[0];
var two   = foo[1];
var three = foo[2];

// with destructuring
var [one, two, three] = foo;
```

---

### 비교연산자

비교연산자는 좌변/우변의 값을 비교하여 그 결과를 **true/false**(참/거짓)로 반환합니다.
비교 연산자는 차후 배울 **if, do…while, while**과 같은 조건분기/반복문과 함께 처리의 분기나 종료 조건을 나타내기 위해 이용하는 것이 일반적입니다.

| 연산자    | 개요(좌변과 우변의 값을 비교)                        | 예              | 결과값    |
| ------ | ---------------------------------------- | -------------- | ------ |
| ==     | 같을 경우, true                              | 5 == 5         | true   |
| ===    | 같을 경우(데이터형 포함), true                     | 5 === 5        | true   |
| !=     | 같지 않을 경우, true                           | 5 != 3         | true   |
| !==    | 같지 않을 경우(데이터형 포함), true                  | 5 !== 3        | true   |
| <      | 좌변이 작은 경우, true                          | 5 < 3          | false  |
| <=     | 좌변이 작거나 같은경우, true                       | 5 <= 5         | true   |
| >      | 우변이 작은 경우, true                          | 5 > 3          | true   |
| >=     | 우변이 작거나 같은경우, true                       | 5 >= 5         | true   |
| ?    : | '**조건식 ? 식1 : 식2**' 조건식이 true인경우 식1, false인경우 식2를 취한다. | (x==1) ? 1 : 0 | 1 또는 0 |



---

#### 등가 연산자(==)

`==`연산자는 좌변/우변의 값을 비교하여 같은 경우에는 true, 같지 않을 경우에는 false를 반환합니다.
그러나 오퍼랜드의 데이터형에 따라 비교의 기준이 다르므로 주의가 필요합니다.

| 좌변과 우변의 형 | 데이터형           | 평가기준                                     |
| --------- | -------------- | ---------------------------------------- |
| 동일        | 문자열/숫자/논리형     | 단순히 쌍방의 값이 동일한지 판단                       |
| 동일        | 배열/객체          | 참조 장소가 동일한지를 판단                          |
| 동일        | null/undefined | 쌍방이 모두 null/undefined 또는 null과 undefined의 비교는 모두 true |
| 틀림        | 문자열/숫자/논리형     | 문자열/논리형을 수치로 변환한 수에 판단                   |
| 틀림        | 객체             | 기본형으로 변환한 후에 판단                          |

위의 표는 등가 연산자의 평가기준을 담은 것 입니다.

---

#### 동치 연산자(===)

동일이라는 뜻으로 사용되는 연산자 입니다.
등가연산자는 `==`를 사용하지만, 동치연산자는 `===`를 사용합니다. 

주로 같은 값인지 아닌지를 판단하는 내용입니다.
그렇기 때문에 결과는 `true`, `false`로 구분합니다.

위의 등가연산자와 같이 설명하겠습니다. 

**등가연산자**의 `==` 표기법과 **동치연산자**의  `===` 표현법이 있습니다.
반대의 개념으로는 `!=`, `!==`의 표현도 있습니다. 이때 사용된 `!`의 의미는 반대의 의미를 가집니다. 
둘은 결과갑의 형태와, 형타입의 형태까지 파악하는 범위에서 결과가 다른 형태를 취합니다. 

즉, `==`의 형태는 자동으로 형변환이 이루어 지면서 비교를 하고, `===`는 형변환이 이루지지 않고 비교를 합니다.

```javascript
var num1 = 254;
var str1 = '254';
console.log(num1 == str1);						// return true
console.log( typeof(num1), typeof(str1) );		
console.log(num1 === str1);						// return false

var num2 = 1;
var boo1 = true;
console.log(num2 == boo1);						// return true
console.log(typeof(num2), typeof(boo1));
console.log(num2 === boo1);						// return false

var und;
var nl = null;
console.log(und);
console.log(nl);
console.log(typeof(und));
console.log(typeof(nl));
console.log(und == nl);							// return true
console.log(und === nl);						// return false

null == false               					// return false
'true' == true              					// return false
true == 2										// return false
```

---

#### 조건연산자(삼항연산자)

```javascript
test ? expression1 : expression2
```

기본적으로 어떠한 내용을 주고 해당하는 식을 `?`를통해 **참/거짓**을 판단하게하고, `:`를 기점으로 
**참이면 왼쪽**, **거짓이면 오른쪽**의 식을 진행하도록 처리하는 구조입니다.

```javascript
var now = new Date();
var greeting = "Good" + ((now.getHours() > 17) ? " evening." : " day.");

console.log(greeting);
```

위 내용에서 `new Date();`는 현재의 시간을 확인하는 메소드입니다.
앞에 `new`라고 붙으면 생성자로 별도로 처리하도록 하게만드는 기능입니다.
현재 시간을 파악하여, `17시`기준 으로 넘으면(**참**) **evening**를 호출, 넘지 않으면 **day**를 호출하도록 되어있습니다.

```javascript
var now = new Date();
var greeting = "Good";
if (now.getHours() > 17){
  greeting += " evening.";
} else {
   greeting += " day.";
}

console.log(greeting);
```

위 내용은 삼항연산자를 사용하지 않을경우에 쓸 수 있는 조건문입니다.
아직 조건문을 배우지 않았지만 위의 삼항 연산자와 동일한 기능을 하도록 처리된 내용으로 판단할 수 있습니다. 

```javascript
var age = 30;
var status = (age >= 18) ? "adult" : "minor";
```



---

### 논리연산자

복수의 조건식(또는 논리 값)을 논리적으로 결합하여 그 결과를 true/false 값으로 건네는 방법입니다.
보통 앞 항에서의 비교 연산자와 조합해서 사용하며, 보다 복잡한 조건식을 표현할 수 있습니다.

| 연산자  | 개요                        | 예                          | 결과   |
| ---- | ------------------------- | -------------------------- | ---- |
| &&   | 좌우 식이 모두 true인 경우, true   | 100 == 100 && 1000 == 1000 | true |
| \|\| | 좌우식의 어느 쪽이든 true인 경우 true | 100 == 100 \|\| 1000 == 50 | true |
| !    | 식이 false인 경우, true        | !(10 > 100)                | true |

위 표는 자바스크립트에서 이용 가능한 논리 연산자 입니다.

---

#### && 연산자

다음의 코드는 && (논리 곱) 연산자의 예제를 보여주고 있습니다.

```javascript
var a1 =  true && true;     		// t && t returns true
var a2 =  true && false;    		// t && f returns false
var a3 = false && true;     		// f && t returns false
var a4 = false && (3 == 4); 		// f && f returns false
var a5 = "Cat" && "Dog";    		// t && t returns Dog
var a6 = false && "Cat";    		// f && t returns false
var a7 = "Cat" && false;    		// t && f returns false
```

---

#### || 연산자

다음의 코드는 || (논리 합) 연산자의 예제를 보여주고 있습니다.

```javascript
var o1 =  true || true;     		// t || t returns true
var o2 = false || true;     		// f || t returns true
var o3 =  true || false;    		// t || f returns true
var o4 = false || (3 == 4); 		// f || f returns false
var o5 = "Cat" || "Dog";    		// t || t returns Cat
var o6 = false || "Cat";    		// f || t returns Cat
var o7 = "Cat" || false;    		// t || f returns Cat
```

---

#### ! (반대)연산자

다음의 코드는 ! (논리 부정) 연산자의 예제를 보여주고 있습니다.

```javascript
var n1 = !true;  		// !t returns false
var n2 = !false; 		// !f returns true
var n3 = !"Cat"; 		// !t returns false
```

##### Conversion rules

###### Converting AND to OR

```javascript
var condition1 = ture;
var condition2 = true;
console.log(condition1 && condition2);
```

위 코드에서 변수 `condition1`의 값은 참(true)입니다, 또 다른 변수 `condition2`의 값도 참(true)입니다.
둘의 결과값은 `true` 로 이해할 수 있습니다. 
위의 내용과 아래 코드의 내용은 항상 같은 결과를 만들어 냅니다. 

```javascript
console.log( !(!condition1 || !condition2) );
```

위 코드의 결과값 또한 참입니다. 
`!`의 연산자의 경우 반대의 개념으로 정리 및 처리하는 기능입니다.



###### Converting OR to AND

```javascript
var condition1 = ture;
var condition2 = true;
console.log(condition1 || condition2);
```

위 코드의 내용 또한 &&연산자의 형태로 변형처리 하루 수 있습니다. 

```javascript
console.log( !(!condition1 && !condition2) );
```



###### Converting between NOTs

자바스크립트의 `!`연산자는 다른언어와 다른 특이한 부분들이 많습니다. 
`!`를 두개이상 사용할 수도 있습니다. 

```javascript
var condition = true;
console.log( condition );						// true
console.log( !!condition );						// true
console.log( !condition );						// false
```

---

##### 중첩된 괄호 제거

논리적인 표현들이 대다수 같은 성격을 가지고 있슶니다.
어떤 규칙에 따라 복잡한 표현에서 괄호를 떼어 내는 것은 항상 가능합니다.



###### 중첩 제거

다음과 같은 합성 작업을 포함한 다음과 같은 합성 작업을 수행합니다.

```javascript
condition1 || (condition2 && condition3)
```

위 내용은 비교연산처리하기위한 내용을 구분하기 위한 괄호를 표기한 내용입니다. 
하지만 실제로 둘을 비교하는 내용에서 우선순위라는 것이 존재하기 때문에 `( )`를 사용할 필요는 없습니다. 
`||` 와 `&&`의 기호는 **&&**를 우선순위로 보고 있습니다. 
즉, 아래의 내용으로 작업하더라도 문제없이 진행됩니다.

```javascript
condition1 || condition2 && condition3
```

반대의 경우는 어떻게 되는 것 일까요?

###### Removing nested OR

```javascript
condition1 && (condition2 || condition3)
```

위의 경우는 `( )`를 감싸지 않으면 `&&`를 먼저 수행하기 때문에, 반드시 `( )`를 처리해 주어야 합니다. 
하지만, 아래의 내용을보면 다른 표현을 수행하고 있습니다. 

```javascript
!(!condition1 || !condition2 && !condition3)
```

다소 복잡하기는 하지만 이전의 코드 내용과 동일한 기능을 하는 내용입니다. 

상황에 따라 다양한 형식과 비교를 하게 되는 경우가 있기에 위 표현식을 이해하고 정리해 두는 것이 필요합니다. 

---

### 콤마 연산자

[콤마 연산자](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Comma_Operator) (`,`)는 두 피연산자를 비교하고, 마지막 피연산자의 값을 반환합니다. 이 연산자는 주로 `for` 반복문 안에서 각각의 시간에 복수의 변수들을 갱신하기 위하여 사용합니다.

예를 들어, a는 각 변에 10개의 원소가 있는 2차원 배열일때, 다음의 코드는 콤마 연산자를 두 변수를 한번에 증가 시키기 위하여 사용하였습니다. 이 코드는 배열의 대각선에 위치한 원소를 출력합니다.

```javascript
for (var i = 0, j = 9; i <= j; i++, j--){
	console.log("a[" + i + "][" + j + "]");
}
```

```javascript
var a, b, c, x, y, z;
a = b = 3, c = 4; 
console.log(a); // 3 (좌-우선)

x = (y = 5, z = 6);
console.log(x); // 6 
```

위 콤마 연산자는 배열, 객체에서 쓰이는 콤마 혹은 함수 매개 변수에서 쓰이는 콤마와는 완전히 다릅니다.
하지만 잘 보면 어떠한 내용을 가지고 있는지 이해할 수 있습니다. 

#### 연산 후 반환

콤마 연산자를 활용하는 또 다른 예제는 반환 전에 연산하는 방법입니다. 언급한대로 항상 마지막에 선언한 요소가 반환되더라도 콤마 전에 있는 표현식이 연산 된 후 반환됩니다. 그래서 다음과 같습니다:

```javascript
function myFunc () {
  var x = 0;

  return (x += 1, x); // ++x 와 같은 효과
}

console.log(myFunc());
```

---

### 비트연산자

[비트단위 연산자](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators) 는 피연산자를 10진수, 16진수, 8진수처럼 취급하지 않고 32비트의 집합으로 취급합니다. 
간단하게 말하자면 2진수로 변환한 후 값을 계산하고 다시 원래의 진수로 전환하여 숫자값을 반환하는 방법입니다.
예를 들면, 10진수의 9는 2진수의 1001로 나타낼 수 있습니다. 
비트 단위 연산자는 이진법으로 연산을 수행하지만, 자바스크립트의 표준 숫자값을 반환합니다..

현시점에서 비트연산자에 대한 내용은 다루지 않습니다. 
비트연산자에 대해 상세하게 이해하고 싶다면 [이곳](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Expressions_and_Operators#비트단위_연산자)을 확인하세요.

---
### 기타연산자

| 연산자        | 개요                      |
| ---------- | ----------------------- |
| ,(콤마)      | 좌우의 식을 계속해서 실행          |
| delete     | 객체의 프로퍼티나 배열의 요소를 삭제    |
| instanceof | 객체가 지정된 클래스의 인스턴스인지를 판정 |
| new        | 새로운 인스턴스를 생성            |
| typeof     | 오퍼랜드의 데이터형을 취득          |
| void       | 미정의 값을 되돌림              |



---

