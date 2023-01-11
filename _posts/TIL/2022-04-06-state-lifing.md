---
title: "State Lifting"
excerpt: "하위에서 일어난 이벤트는 상위에서 어떻게 적용할 수 있을까"

categories: react
tags: [react, state lifting]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

React의 데이터 흐름은 상위 컴포넌트에서 하위 컴포넌트로 전달하는 하향식 단방향 흐름을 원칙으로 가진다.

만약 하위 컴포넌트에서 어떤 이벤트로 상위 컴포넌트의 상태가 바뀌는 상황에서는 어떻게 할 것인가? 이러한 경우에 **State Lifting(상태 끌어올리기)**를 적용하면 된다.

**State Lifting**은 상위 컴포넌트에 정의된 상태를 변경하는 함수(handler) 자체를 하위 컴포넌트에 props로 전달하고, 하위 컴포넌트에서 이 함수를 실행하는 것이다.

먼저 부모 컴포넌트에 상태를 변경하는 함수를 만들고 자식 컴포넌트에 그 함수를 props를 통해 전달하여 자식 컴포넌트에서 함수를 실행하면된다.

![](https://media.vlpt.us/images/hyeun427/post/9fa6d8b5-7614-4c8b-add8-0dc5dc0555e1/image.png)

이미지 출처 https://foamless.tistory.com/730
