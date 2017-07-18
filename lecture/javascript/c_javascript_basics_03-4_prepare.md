# javascript 기초_6_재정리 필요

지난 시간동안 우리는 기초 문법에 대해 배웠습니다.
이는 `javascript-3`의 내용들이 대부분입니다.
이번시간에는 `javascript-5`의 내용으로 추가된 기능들을 좀더 눈여겨 보도록 하겠습니다.
차후 `javascript-2015` 즉, ECMA6의 기능을 이해하기 전 조금씩 추가되는 기능들을 이해하고 진행해야 합니다.

---

[TOC]

---

## 좀더 이롭고 새로운 메소드

1. indexOf()
2. filter
3. forEach()
4. map()
5. reduce()

---

### indexOf()

`indexOf()`의 기능은 배열에서 특정값을 찾을 때 사용하는 기능입니다.
과거 특정값을 찾기위해 우리는 **for loop**를 사용하여 찾을 수 밖에 없었습니다. 

```javascript
var isExist = false;
for(var i = 0; max = array.length; i++){
  if( array[i] === '특정값'){
    isExist = true;
  }
}
```

위 내용은 `특정값`을 찾아내기 위한 코드중의 하나입니다. 
값을 찾아내기 위해 많은 줄을 사용하여야 하는 다소 불필요한 내용중의 하나로 볼 수 있습니다. 
위코드를 이제 우리는 이렇게 대처해서 사용할 수 있습니다.

```javascript
var isExist = (array.indexOf('특정값') !== -1);
```



---

### filter()

```javascript
var arr = [
  {'name':'apple','count':2},
  {'name':'orange','count':3},
  {'name':'pear','count':5},
  {'name':'orange','count':9},    
];
var newArr = arr.filter(function(item){
  return item.name === 'orange';
});

console.log('filter result', newArr);
```

위 내용은 `newArr`은 `name`이 `orange`인 것만 필터링 되어서 나오도록 되어진 코드입니다.

---

### forEach()

자바스크립트 성능 최적화 기능에서 보면 forEach()보다 for가 더 좋다고 나옵니다. 
하지만 실제로는 **1ms**의 시간도 차이가 나지 않는다는 내용이 작성되어져 있습니다. 
결국 가이드에는 사용상의 문제가 없다는 결론으로 치부되기 때문에 
사용하는데 전혀 문제 없는 코드입니다. 

```javascript
var array = [1,2,3,4,5];
array.forEach(function( v,i ){
  if(v === 3){
    console.log(v + ":" + i);					// 3 : 2 결과 도출
  }
});
```



---

### map()

map의 기능은 forEach와 기능이 미세하게 다릅니다. 

```javascript
var numArr = [1,2,3,4,5];
var bType = numArr.forEach( function(v, i){
  console.log(v); 
  return v+1;
});

var cType = numArr.map(function(v,i){
  console.log(v);
  return v+1;
});
```

`bType`과 `cType`의 실행에의한 내용은 다르다는 것을 알 수 있습니다.
`bType`는 `undefined`가 나오며, `cType`는 `[2,3,4,5,6]` 이라는 배열값이 나오게 됩니다. 
즉, 배열을 가지고 연산을 하고 길이가 같은 배열로 결과를 **return**처리하려고 한다면 map을 사용하는 것이 훨씬 유리합니다. 

둘의 용도가 다른 것을 기억하세요.

---

### reduce()

```javascript
array.reduce(f,n);
var a = [1,2,3,4,5];		// 'f'는 함수, 'n'은 두번째 인자 라고 가정
```

```javascript
// 'n'이 없을 경우 array.reduce(f);를 확인
// f의 
(0) iteration
- 첫번째 인자 : 1
- 첫번째 인자 : 2

(1) iteration
- 첫번째 인자 : 1,2
- 첫번째 인자 : 3

(2) iteration
- 첫번째 인자 : 1,2,3
- 첫번째 인자 : 4

(3) iteration
- 첫번째 인자 : 1,2,3,4
- 첫번째 인자 : 5
```

```javascript
즉, f의 인자가 f(a,b,c,d) 라면
a = 이전값
b = 현재값
c = 인덱스
d = 배열
```

하지만 reduce 메소드를 불러올 때 n을 주게되면, f의 첫번째 인자가 n이 되게 되는데 즉 이전 초기값이 n으로 대체됩니다 

```javascript
var a = ['a','b','c','d','e','a','b','a','c','c','c'];
var b = a.reduce(function(x,y){
  console.log('x: ', x);
  console.log('y: ', y);
  x[y] = ++x[y] || 1;
  return x;
},{});

console.log(b);
```

위 예제를 돌려서 확인해보면 `b`는 최종적으로 
`Object{a:3, b:2, c:4, d:1, e:1}`로 리턴되는 것을 알 수 있습니다