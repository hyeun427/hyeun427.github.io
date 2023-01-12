---
title: "==과 ==="
excerpt: "값은 같지만 타입은 다르다고?"

categories: javascript
tags: javascript, operator]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

자바스크립트에서 ==와 ===의 차이는 무엇일까!

## 1. ==

x==y의 경우에 x의 '값'과 y의 '값'이 같은지를 검사한다.

<br>

## 2. ===

x===y의 경우에 x와y의 '값과 타입'이 같은지를 검사한다.

## 3. 간단한 예제

간단한 예제를 보면서 정리해보자.

```jsx
var a = 1;
var b = "1";

a == b; // true	// 값만 비교하기때문에 a의 값인 1과 b의 값인 1이 같아서 true
a === b; // false // 값과 타입 둘다 비교하기 때문에 a는 숫자와 b는 문자로 타입이 다르기 때문에 false
```
