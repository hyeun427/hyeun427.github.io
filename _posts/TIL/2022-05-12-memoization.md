---
title: "memoization"
excerpt: "반복 사용되는 값을 저장해서 사용하자!"

categories: react
tags: [react, memoization]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## Memoization

메모이제이션이란 프로그래밍을 할 때 반복되는 결과를 메모리에 저장해서 다음에 같은 결과가 나올 때 빨리 실행하는 코딩 기법이다.

피보나치수열을 예시로 이해할 수 있다. 피보나치 수열은 가장 앞의 두 수는 주어지고 그 다음 수부터는 앞 두 개의 수를 더한 값이 다음 값이 되는 수열이다. 메모이제이션을 활용하여 피보나치 수열의 n번째 항의 값을 반환하는 함수를 구현해보자.

```jsx
const fiboRecMemoized = (() => {
// 계산 결과를 저장하는 저장소를 만든다
  const memo = new Map(); const fiboRec = n => {
    // 만약에 이전에 같은 인수로 계산한 적이 있다면
    // 해당 결과를 바로 반환합니다.
    let result = memo.get(n);
    if (result != undefined) return result;

    result = (
      n < 1 ? 0 :
      n === 1 ? 1 :
      fiboRec(n - 1) + fiboRec(n - 2) );
    // 계산 결과를 저장소에 저장한 후 반환합니다.
    memo.set(n, result); return result; } return fiboRec; })();

```

<br>
<br>

[참고](https://kjwsx23.tistory.com/214)
