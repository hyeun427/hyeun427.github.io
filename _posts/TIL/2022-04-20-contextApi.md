---
title: "context api, redux, mobx, swr"
excerpt: "데이터 관리 어떻게 할래?"

categories: react
tags: [react, context api, redux, mobx, swr]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## 1. context api

- context api는 컴포넌트 안에서 전역적으로 데이터를 공유하도록 나온 개념이다.
  3가지 주요 개념으로 createContext, Provider, Consumer가 있다.

<br>

### createContext

- context 객체를 만들때 사용하는 함수이다.
- createContext함수를 호출하면 Provider와 Consumer 컴포넌트를 반환한다.

<br>

### Provider

- 정의한 context를 하위 컴포넌트에게 전달하는 역할을 한다.
- Provider를 사용할 때에는 value를 사용해야한다.
- 전달받는 컴포넌트의 수는 제한이 없다.
- provider하위에 context를 가진 component는 provider의 value로 가진 state가 변화할 때마다 리렌더된다.

### Consumer

- context 변화를 구독하는 컴포넌트이다.
- 설정한 값을 불러올 때 사용한다.

---

## 2. redux

리덕스란 자바스크립트의 상태 관리 라이브러리이다. 리덕스에는 세 가지 원칙이 있다.

- 동일한 데이터는 항상 같은 곳에서 가지고 온다.
- state는 읽기만 가능하고 액션이라는 객체를 통해서만 상태를 변경할 수 있다.
- 변경은 순수함수로만 가능하다.

---

## 3. mobx

MobX는 전역 상태 라이브러리이다. 모든 상태변화롤 일어나는 부분으로 자동으로 추적해주는 역할을 한다.

redux와 차이점은 mobx는 객체지향적이고 redux보다 사용이 쉽다. 단일 스토어를 강제하지 않는다.

---

## 4. swr

SWR은 캐시(스태일)로부터 데이터를 반환한 후, fetch 요청(재검증)을 하고, 최종적으로 최신화된 데이터를 가져온다.
