---
title: "useContext"
excerpt: "리액트 훅스 공부하기"

categories: react
tags: [react, useContext]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

![업로드중..](blob:https://velog.io/c47ac2dd-0ac9-43b5-ba20-1d3c4825a42f)

## 1. Context

리액트로 만든 앱은 여러개의 컴포넌트들로 이루어져있다. 최상위 App 컴포넌트에서 시작해서 트리형태로 쭉쭉 뻗어나간다. 리액트에서의 일반적인 데이터 흐름은 부모 컴포넌트에서 자식 컴포넌트로(위에서부터 아래로) props로 전달된다. props를 사용해서 데이터를 전달할 때는 부모 컴포넌트가 자식 컴포넌트 태그에 일일이 props를 넣어서 단계별로 전달해줘야 한다.

엄청 큰 리액트 App이 있다고 가정해보자. 앱 내부에서 수많은 컴포넌트들이 공통적으로 필요한 전역적인 데이터(현재 로그인된 사용자 정보, 테마, 언어 등)가 있을 수 있다. 이때 이런 전역적인 데이터를 **props로 일일이 단계적으로 전달**(prop-drilling) 해야 한다면 너무 복잡할 것이다. 이 방법은 코드를 수정할때도 문제가 많다. 리액트는 이러한 문제점을 간편하게 해결해주는 Context-API라는 것을 제공해준다.

Context는 앱 안에서 전역적으로 사용되는 데이터들을 여러 컴포넌트들끼리 쉽게 공유할 수 있는 방법을 제공한다. Context를 사용하면 props로 일일이 데이터를 전달해주지 않아도 데이터를 가지고 있는 상위 컴포넌트가 데이터가 필요한 하위 컴포넌트들에게 전달해줄 수 있다. 그 하위 컴포넌트가 트리안에 어디에 위치해있건 상관없이 말이다. 그래서 Context는 전역적인 데이터를 전달하기에 굉장히 유용하다.

**Prop Drilling 의 문제점**

데이터가 필요없는 중간 컴포넌트들도 데이터를 받아야하기 때문에 코드가 복잡하고 더러워진다. 만약 데이터를 전달하는 과정에서 잘못 전달하거나 데이터를 수정해버리면 모든 상위 컴포넌트들을 찾아니면서 에러를 해결해야한다.

## 2. useContext

props 대신 context를 사용해서 데이터를 공유하면 한곳에 있는 데이터를 모든 자녀 컴포넌트들에게 데이터를 쉽게 넘겨줄 수 있다. 그 데이터를 사용하고 싶은 컴포넌트들은 useContext 훅을 사용해서 그냥 받아오기만 하면 된다. useContext는 context로 공유한 데이터를 쉽게 받아올 수 있게 도와주는 역할을 한다.

하지만 Context는 꼭 필요할때만 사용해야한다. context를 사용하면 컴포넌트를 재사용하기 어려워 질 수 있다. 왜냐하면 Context의 주된 목적은 다양한 레벨에 있는 많은 컴포넌트들에게 전역적인 데이터를 전달하기 위함이기 때문이다. 리액트 공식문서에는 context를 사용하는 이유가 단지 Prop drilling을 피하기 위한 목적이라면 Component Composition (컴포넌트 합성)이 더 간단한 해결책일 수 있다고 제안하고 있다.

## 3. useContext 사용 방법

#### 1) createContext를 import 해주기

![](https://velog.velcdn.com/images/hyeun427/post/cee789cf-47e8-43bd-99b5-d108a1dbb47e/image.png)

#### 2) 최상위 컴포넌트에 Provider를 감싸주고 value로 내려주기

![](https://velog.velcdn.com/images/hyeun427/post/ff2c6fa9-eca0-4c95-a88a-5850506dcd63/image.png)

#### 3) 필요한 곳에 useContext 사용하기

![](https://velog.velcdn.com/images/hyeun427/post/306469c3-40a7-4626-9b8e-9f567b3d991b/image.png)

---

> 본 글은 [별코딩](https://youtu.be/LwvXVEHS638) 영상을 보고 작성한 글입니다!
