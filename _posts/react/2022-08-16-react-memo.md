---
title: "React.memo"
excerpt: "리액트 훅스 공부하기"

categories: react
tags: [react, React.memo]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

![](https://velog.velcdn.com/images/hyeun427/post/a4832868-3069-4949-924a-af2500a8d635/image.gif)

## 1. React.memo

React는 성능이 굉장히 좋기때문에 대부분의 경우, 컴포넌트의 렌더링 횟수에 대해 걱정할 필요는 없다. 하지만 렌더링이 지나치게 자주 발생하거나 매번 렌더링마다 무거운 로직을 처리해서 성능에 부담을 준다면 불필요한 렌더링을 줄여야 할 것이다.

React에서는 기본적으로 부모 컴포넌트가 렌더링이 되면 자식 컴포넌트도 자동으로 렌더링 된다.

React.memo는 React에서 제공하는 고차 컴포넌트(HOC,Higher Order Component)이다. 고차 컴포넌트란 어떤 컴포넌트를 인자로 받아서 새로운 컴포넌트를 반환해주는 함수이다. 즉, React.memo라는 고차 컴포넌트에 보통 컴포넌트를 인자로 주어 최적화된 컴포넌트를 반환해주는 것이다. 이렇게 최적화가 된 컴포넌트는 렌더링이 되어야 할 상황에서 Prop Check를 해서 렌더링이 되어야하는지 확인하고, 이때 Props에 변화가 있다면 렌더링을 하고, 변화가 없다면 새로 렌더링 하지않고 기존의 정보를 재사용한다.

React.memo의 memo는 Memoization을 뜻한다. Memoization은 이미 계산해놓은 값을 메모리 상에 저장해놓고 필요할 때마다 꺼내서 재사용하는 기법이다.

React.memo는 꼭 필요할 때만 사용해야한다. 무분별한 사용은 오히려 성능에 좋지않다. 컴포넌트를 Memoizing 할 때 컴포넌트를 어딘가에 저장해놔야 하기때문에 메모리를 추가적으로 소비하기 때문이다.

React.memo를 사용하기에 적합한 상황은 `1) 컴포넌트가 같은 Props로 자주 렌더링 될 때, 2) 컴포넌트가 렌더링이 될 때마다 복잡한 로직을 처리해야할 때` 이다.

React.memo는 오직 Props 변화에만 의존하는 최적화 방법이다. 따라서 상태와 관련된 Hook(useState, useReducer, useContext 등)을 사용한다면 Props 변화와 상관없이 상태 변화가 있다면 렌더링 되는 사실을 알고 있어야한다.

## 2. React.memo 사용 방법

![](https://velog.velcdn.com/images/hyeun427/post/3597f7b2-5308-4cc4-813b-e156aa79936c/image.png)

자식 컴포넌트를 `memo`로 감싸주면 끝!

---

> 본 글은 [별코딩](https://youtu.be/oqUgcxwrnSY) 영상을 보고 작성한 글입니다!
