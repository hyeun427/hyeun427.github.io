---
title: "props와 state"
excerpt: "실시간으로 값이 변경되도록 설정해보자"

categories: react
tags: [react, props, state]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## props

### 1. props란?

- props는 properties의 줄임말이다.
- 부모 컴포넌트가 하위 컴포넌트에 값을 전달 할 때 사용한다.(단방향)
- props값은 부모 컴포넌트에서 설정할 수 있다. 자식 입장에서는 읽기전용 데이터!

### 2. 사용방법

- 프로퍼티에 문자열을 전달할 때는 큰따옴표(" ")를, 문자열 외의 값을 전달할 때는 중괄호({ })를 사용 한다.

## state

### 1. state란?

- 컴포넌트 내부에서 변경 가능한 데이터를 관리할 때 사용한다.
- 값을 저장하거나 변경할 수 있는 객체로 보통 이벤트와 함께 사용된다.

### 2. 사용방법

```
 const [ 데이터, 데이터변경함수 ] = useState(초기값(생략가능));

```

### 3. state 값 바꾸는 방법

- 반드시 setState()함수를 이용하여 변경해야한다.
