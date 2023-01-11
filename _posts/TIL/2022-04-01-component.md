---
title: "component"
excerpt: "클래스형 컴포넌트와 함수형 컴포넌트 어떤게 더 편할까?"

categories: react
tags: [react, import, export]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## Component

1. 컴포넌트란?
   - 독립적인 기능을 수행하는 최소한의 단위 모듈이다.
   - 데이터(props)를 입력받아 View(state) 상태에 따라 DOM Node를 출력하는 함수
   - 컴포넌트는 항상 대문자로 시작해야한다.
   - 컴포넌트의 종류에는 크게 함수형 컴포넌트와 클래스형 컴포넌트 2가지가 있다.
     <br />
2. Props와 State는 무엇인가?
   - **props**는 부모 컴포넌트가 자식 컴포넌트에게 주는 값이다.어떠한 값을 컴포넌트에 전달해 줘야 할때 사용하며 할당된 후 컴포넌트 내부에서 값을 변경할 수 없다. **state**는 컴포넌트 내부에서 선언하며 내부에서 값을 변경할 수 있다. 동적인 데이터를 다룰 땐 state를 사용한다.

## 클래스형 컴포넌트 / 함수형 컴포넌트

1. 기본 구조
   ![](https://images.velog.io/images/hyeun427/post/0833c02f-d417-4f01-8c2a-947b3285493c/%ED%81%B4%EB%9E%98%EC%8A%A4%ED%98%95%ED%95%A8%EC%88%98%ED%98%95.png)

<br>
2. 구조 특징

- 클래스형 컴포넌트는 render함수를 필수적으로 사용하여 return 안의 코드를 화면에 보이도록 렌더링한다.

- 함수형 컴포넌트는 스스로가 렌더함수이기때문에 render함수를 사용할 필요가 없다. 데이터를 가진 하나의 props객체 인자를 받은 후 React 엘리먼트를 반환한다.
