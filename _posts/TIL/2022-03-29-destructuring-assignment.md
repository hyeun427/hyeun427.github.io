---
title: "구조분해할당과 나머지 매개변수"
excerpt: "개별 값을 새로운 개별 변수에 담아보자"

categories: javascript
tags: [javascript, Destructuring Assignment, Rest parameter]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## Destructuring Assignment(구조 분해 할당)

<br />
구조 분해 할당이란 배열이나 객체의 속성을 해체하여 그 값을 개별 변수에 담을 수 있게 하는 JavaScript 표현식이다.
<br /><br />

1. 기본 할당 구문은 아래와 같다.

```
var a, b;

[a=5, b=7] = [1];
console.log(a); // 1
console.log(b); // 7

```

- 구조 분해 할당의 좌변은 값을 넣을 변수, 우변에는 값이 되는 변수가 된다.
  <br />

2. 클래스 컴포넌트에서는 props 또는 state를 보통 render()안에서 분해한다.
   <br />

---

## Rest parameter(나머지 매개변수)

<br />
나머지 매개변수는 매개변수 이름 앞에 ... 점이 3개 붙여서 정의한 매개변수이다.
<br />

**특징**<br />

1. 나머지 매개변수는 항상 마지막에 있어야 한다. 남아있는 인수를 모으는 역할을 하기 때문이다.
2. 나머지 매개변수는 함수에 전달하는 인자들을 배열로 전달한다.
3. 배열이기 때문에 배열 메서드를 사용할 수 있다.(length, map 등)
4. 인수 개수에 제한이 없는 함수를 만들 때 나머지 매개변수를 사용한다.
