---
title: "flatten, unflatten"
excerpt: "배열을 정리하자!"

categories: javascript
tags: javascript, flatten, unflatten]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### Flatten

자바스크립트에서 Flatten은 array 구조 안에 또 다른 array를 인덱스로 가질 때, array를 평평하게 만드는 작업이다.

Array의 메서드인 flat() 함수를 사용한다.

flat() 메서드는 모든 하위 배열 요소를 지정한 깊이까지 재귀적으로 이어붙인 새로운 배열을 생성한다.

예시를 보면서 이해해보자.

```jsx
const arr1 = [1, 2, [3, 4]];
arr1.flat();
// [1, 2, 3, 4]

const arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
// [1, 2, 3, 4, [5, 6]]

const arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
// [1, 2, 3, 4, 5, 6]

const arr4 = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];
arr4.flat(Infinity);
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

arr1는 \[ , , \[]] 구조이기때문에 flat()을 한번만 하면 \[3,4]이 평탄화된다.
arr2는 배열 구조(1번 배열이라하자) 안에 배열(2번 배열이라하자)이, 그 배열(2번 배열) 안에 또 배열(3번 배열)이 있는 구조이기때문에 flat()을 한번 실행하면 2번배열이 평탄화 되고, 그 결과를 한번 더 flat() 실행하면 남은 3번 배열이 평탄화 된다. 몇 개의 배열이 중첩되어있는지 확인하고 메서드를 사용하면 평탄화가 어렵지 않다!

<br>

### Unflatten

Unflatten은 flatten과 반대로 배열을 중첩시켜주는 기능이다. 메서드가 따로 있는지는 구글링에서 찾지 못했고, npm에서 unflatten을 찾긴 했다.

[npm의 unflatten](https://www.npmjs.com/package/unflatten)

<br><br>

---

[Reference](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/flat)
