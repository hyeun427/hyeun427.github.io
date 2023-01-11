---
title: "useEffect와 useRef"
excerpt: "리액트 훅을 쓰면 훨씬 효율적이라고!"

categories: react
tags: [react, react Hook, useEffect, useRef]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## useEffect

useEffect는 컴포넌트가 렌더링 될 때마다 어떠한 작업을 수행하게 설정하는 HOOK이다.

컴포넌트가 그려진 이후에 실행되기 때문에 클래스형 컴포넌트에서 사용하는 생명주기 메서드 중 componentDidMout, componentDidUpdate의 기능을 합친 형태라고 생각 할 수 있다.

useEffect의 문법 구조는 아래와 같다.

```jsx
useEffect(() => {
  console.log("마운트 될 때만 실행");
}, []);
```

위 구조에서 [] 부분은 의존성 배열이라고 부른다. 이 의존성 배열 안에 있는 요소가 변경될 때 함수가 실행되며 만약 의존성 배열을 생략하고 작성한다면 변경되는 모든 사항마다 실행하게 된다.

---

## useRef

우선, Ref는 리액트에서 DOM을 선택해 직접 접근할 때 사용한다. useRef는 함수형 컴포넌트에서 설정할 때 사용한다.

useRef는 DOM 선택하는 용도 말고 한가지의 용도가 더 있다. 컴포넌트 안에서 변수를 관리하는 기능이다. useRef으로 관리하는 변수는 값이 바뀐다고 해서 컴포넌트가 리렌더링되지 않는 것이 가장 큰 특징이다.

또 useRef Hook으로 만들어진 변수는 함수를 다시 호출하더라도 마지막으로 업데이트한 current 값이 유지되는 장점이 있어서 scroll 위치 등에 유용하게 쓰인다.

## useEffect와 useRef

useEffect와 useRef를 함께 사용하는 예로는 자동포커스, 스크롤바 컨트롤 등이 있다.

```jsx
const inputRef = useRef < HTMLInputElement > null;

useEffect(() => {
  inputRef.current?.focus();
}, []);

return <input type="password" ref={inputRef} />;
```
