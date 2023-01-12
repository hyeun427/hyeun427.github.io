---
title: "Custom Hooks"
excerpt: "리액트 훅스 공부하기"

categories: react
tags: [react, Custom Hooks]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## 1. Custom Hooks이란?

커스텀 훅이란 단어 그대로 우리의 입맛대로 직접 만들어서 사용할 수 있는 훅이다. 커스텀 훅을 만드는 방법은 간단하다. 원하는 이름을 지어주고 원하는 기능을 가진 함수를 하나 만들면 된다. 간단히 말하면 컴포넌트 내부에 있던 로직을 커스텀 훅으로 빼주는 것이다. 물론 매개변수와 return 값도 원하는대로 정할 수 있다.

커스텀 훅의 매력적인 점은 커스텀 훅 내부에서 다른 리액트 훅도 사용할 수 있다는 것이다. 커스텀 훅을 사용하는 컴포넌트마다 가지는 커스텀 훅이 가지는 state나 effect 값은 독립적이기 때문에 커스텀 훅은 폭발적인 재사용성을 제공한다.

## 2. Custom Hooks 사용 예제

![](https://velog.velcdn.com/images/hyeun427/post/742ed449-de24-44ef-8270-dda8d5089f07/image.gif)

![](https://velog.velcdn.com/images/hyeun427/post/871ae0cb-9af8-4e6d-afd3-9a08fb469acb/image.png)

커스텀 훅인 `useInput` 코드를 살펴보자.
매개변수로 `initialValue`와 `submitAction`을 받고 `initialValue`를 useState의 초기값으로 넣어준다.

`handleChange`함수는 인풋 박스에 사용자가 작성할 때 작성값을 받아오기 한 함수이다. `handleSubmit`은 인풋 박스 옆 확인 버튼을 눌렀을 때 처리되는 로직을 넣었다.

반환값으로는 `inputValue`, `handleChange`, `handleSubmit`을 주어 다른 여러 컴포에서 사용할 수 있도록 하였다.

메인 컴포넌트를 보면 초기값으로는 `""`, `submitAction`에 `displaymsg`를 넣은 `useInput`을 import해서 사용하였다.

이렇게 커스텀 훅을 사용하면 공통적으로 쓰이는 함수 코드를 계속 작성하지않고 한 줄로 간단하게 import해서 코드를 줄일 수 있다.

---

> 본 글은 [별코딩](https://youtu.be/tdORpiegLg0) 영상을 보고 작성한 글입니다!
