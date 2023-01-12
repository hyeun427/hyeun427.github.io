---
title: "useEffect"
excerpt: "리액트 훅스 공부하기"

categories: react
tags: [react, useEffect]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## 1. useEffect란

어떤 컴포넌트가 Mount(마운트-화면에 첫 렌더링), Update(업데이트-다시 렌더링) 혹은 UnMount(마운트 해제-화면에서 사라질 때) 되었을 때 특정 작업을 처리할 코드를 실행시키고 싶다면 useEffect를 사용하면 된다.

useEffect는 인자로 콜백함수를 받는다.

콜백함수란 다른 함수의 인자로 전달된 함수를 의미한다. 이 콜백함수 내부에 우리가 원하는 작업을 처리해 줄 코드를 적어주면 된다.

## 2. useEffect 형태와 특징

![](https://velog.velcdn.com/images/hyeun427/post/fcb10462-9b7f-4203-a0f4-19de9e9125e8/image.png)

1번 형태는 인자로 하나의 콜백함수만 받는 경우이다. 컴포넌트가 렌더링이 될 때 마다 매번 콜백이 실행된다. 맨 처음 화면에 렌더링될 때와 리렌더링될 때 모두 실행된다.

2번 형태는 첫 번째 인자로는 콜백함수, 두 번째 인자로는 의존성 배열을 받는 경우이다. 맨 처음 화면에 렌더링 될 때 그리고 배열안에 들어있는 요소(value)의 값이 바뀔때만 실행된다. 만약 의존성 배열을 빈 배열로 전달할 경우 컴포넌트가 맨 처음 화면에 렌더링 될 때만 실행이 된다.

```js
// 1. 컴포넌트가 렌더링 될 때마다 매번 콜백 실행.
useEffect(() => {
  // 작업
});

// 2. 맨 처음 + value 값이 바뀔 때 실행.
useEffect(() => {
  // 작업
}, [value]);

// 3. 맨 처음 한번만 실행.
useEffect(() => {
  // 작업
}, []);
```

> 렌더링 될 때마다 실행되는 것을 확인 할 수 있다.
> ![](https://velog.velcdn.com/images/hyeun427/post/28e1f740-5586-459c-8cdb-a96bf621663d/image.gif)

![](https://velog.velcdn.com/images/hyeun427/post/5f124a29-3c22-49ca-a04c-e6b21c2454a3/image.gif)

> count 값이 변경 될 때만 콜백함수가 실행된다!
> ![](https://velog.velcdn.com/images/hyeun427/post/9febde3b-4a4b-46d2-b09c-d46c1139a9ce/image.gif) > ![](https://velog.velcdn.com/images/hyeun427/post/568aa17f-5159-4e01-9309-6b3e2e0f3194/image.png)

## 3. Clean Up

Clean-up함수란 useEffect()에서 parameter로 넣은 함수의 return 함수이다.

```js
useEffect(() => {
  // 작업

  return () => {
    // 작업 정리
  };
}, []);
```

![](https://velog.velcdn.com/images/hyeun427/post/8a4185d2-3855-40b5-864f-39f400f6b1b7/image.png)

useEffect를 사용할 때 위처럼 빈 배열을 두번째 인자로 넣어주면 useEffect가 화면이 처음 렌더링 될 때만 실행되고 return문에 클린업 함수를 넣어줌으로써 Timer 컴포넌트가 Unmount 될 때, 즉 Timer 컴포넌트가 화면에서 사라질 때 Timer를 끝내는 클린업 함수가 실행된다.

---

> 본 글은 [별코딩](https://youtu.be/G3qglTF-fFI) 영상을 보고 작성한 글입니다!
