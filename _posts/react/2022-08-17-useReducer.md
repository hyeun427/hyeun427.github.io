---
title: "useReducer"
excerpt: "리액트 훅스 공부하기"

categories: react
tags: [react, useReducer]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

![](https://velog.velcdn.com/images/hyeun427/post/1b0fee9c-d708-477a-990b-1620dba69681/image.png)

## useReducer

컴포넌트의 state를 생성하고 관리하기 위해서 useState를 사용해왔다. 하지만 리액트에서 state 관리를 위한 또 다른 훅이 있다. 바로 useReducer 라는 훅이다.

useReducer는 useState 처럼 state를 생성하고 관리할 수 있도록 도와주는 도구이다. 그렇다면 useReducer는 언제 사용하는 것일까? **여러 개의 하위 값을 포함하는 복잡한 state(아래와 같은 state)를 다뤄야할 때 useReducer를 사용하면 깔끔하게 코드를 작성할 수 있다.**

```js
{
	teacher: 'James',
    student: ['Kim','Amy','John'],
	count : 3,
    locations: [
      {country: 'Korea', name: 'A'},
      {country: 'Australia', name: 'B'}
    ]
}
```

useReducer는 `Dispatch`, `Action`, `Reducer`로 이루어져있다.

만약 철수와 은행 그리고 거래내역이 있다고 가정해보자. 철수의 거래내역은 철수가 직접 수정하는 것이 아니라 은행이 철수의 요구대로 대신 업데이트 해준다.
여기서 이 거래내역을 state 라고 한다면 은행을 Reducer라고 할 수 있다. Reducer 는 state 를 업데이트 해주는 역할을 한다. 컴포넌트의 state를 변경하고 싶다면 꼭 이 Reducer를 통해서 해야되는 것이다. 마치 철수가 거래내역을 업데이트하기 위해선 은행이 대신 해줘야 하는 것처럼 말이다.
철수는 거래내역이라는 state를 변경하기 위해 은행에게 **요구**라는 것을 한다. 이 요구라는 행위를 `Dispatch`라고 할 수 있다. 그리고 '만원을 출금해주세요'라는 **요구(Dispatch)의 내용**을 `Action`이라고 한다.
철수는 요구라는 Dispatch 안에 만원을 출금해주세요 라는 내용의 Action을 담아서 은행이라는 Reducer에 보냄으로써 state를 변경할 수 있는 것이다.
그러면 Reducer(은행)는 Action(요구사항)의 내용대로 state(거래내역)를 변경해준다.
철수는 은행에게 여러가지 다른 액션들을 보냄으로써 복잡한 일을 할 수 있다. 철수의 액션을 알아서 처리해주는 Reducer는 복잡한 일을 하는데 있어서 아주 최고라고 할 수 있다.

---

> 본 글은 [별코딩](https://youtu.be/tdORpiegLg0) 영상을 보고 작성한 글입니다!
