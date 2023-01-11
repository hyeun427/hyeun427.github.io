---
title: "state와 prev"
excerpt: "쓰임에 맞게 효율적으로 데이터 반영하자!"

categories: react
tags: [react, state, prev]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

State는 리액트 컴포넌트에서 데이터를 담기위한 상자이다.
이 상자는 함수가 모두 끝나게 되면 담긴 내용들이 화면에 반영이된다.

아래의 코드를 살펴보자.

```jsx
function handleClick() {
  setCount(count + 1); // 현재 count는 0 + 1 => 1을 상자에 담는다.
  setCount(count + 1); // 1 이 상자에 담겼지만 여전히 count는 0 이므로 1이 상자에 담긴다
  setCount(count + 1); // ...
  setCount(count + 1); // ...
  setCount(count + 1); // 같은 방식으로 최종적으로 1이 상자에 담겨 화면에 1이 반영된다
}
```

<br />
 이 함수가 실행이 되면 한번에 5가 증가하길 기대하겠지만 state는 함수가 모두 끝나야 적용이 되기때문에 count가 초기값 0에서 변하지않고 계속 0+1이 되어 결국 1만 증가한다.

만약 한번에 5가 증가하길 원한다면 어떻게 해야할까? 이럴때 prev를 사용하면 된다.

```jsx
function handleClick() {
  setCount((prev) => prev + 1); // 임시저장공간의 0(기본값, prev) + 1 => 1을 상자에 담는다.
  setCount((prev) => prev + 1); // 임시저장공간에 담긴 1(prev) + 1 => 2를 상자에 담는다.
  setCount((prev) => prev + 1); // ...
  setCount((prev) => prev + 1); // ...
  setCount((prev) => prev + 1); // 같은 방식으로 최종적으로 5가 상자에 담겨 화면에 5가 반영된다
}
```

prev는 임시저장공간에 저장한다. 그렇기 때문에 state와 다르게 함수가 진행되는
상황에서 "0+1 => 1+1 => 2+1 => 3+1 => 4+1 => 5" 의 로직으로 반영된다.

상황에 따라 state나 prev를 잘 선택해서 사용한다면 매우 효율적일 것이다.
