---
title: "useCallback"
excerpt: "리액트 훅스 공부하기"

categories: react
tags: [react, useCallback]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

![](https://velog.velcdn.com/images/hyeun427/post/69dfb6e5-69be-4bb1-9736-23ccddc82186/image.gif)

## 1. useCallback과 Memoization

useCallback은 Memoization 기법으로 **컴포넌트의 성능을 최적화**시켜주는 도구이다.
우선 Memoization이 무엇인지 복습해보자.
Memoization이란 자주 사용되는 값을 받아오기 위해 반복적으로 계산을 해야한다면 이전에 이미 계산해둔 `값`을 캐싱해서 메모리에서 꺼내서 재사용하는 최적화기법이다. useMemmo에 인자로 콜백함수를 넣어주면 콜백함수가 `return 해주는 값`을 memoization 해주는 것이다.

useCallback이란 인자로 전달한 콜백함수 자체를 memoiaztion해서 사용하는 것이다. 재사용하고 싶은 함수를 useCallback으로 감싸주면 필요한 곳에서 재사용할 수 있다.

## 2. useCallback의 구조

```js
useCallback(() => {
  return value;
}, [item]);
```

useCallback은 두개의 인자를 받는다. 첫 번째 인자로는 memoiaztion 해줄 콜백 함수, 두 번째 인자로는 의존성 배열을 받는다.

아래의 예시를 보자.

```js
const calculate = useCallback(
  (num) => {
    return num + 1;
  },
  [item]
);
```

이렇게 함수를 useCallback으로 감싸주면 calculate 변수는 메모이제이션 된 함수를 가지고 있게 된다. 이 메모이제이션 된 calculate 함수는 두번째 인자인 의존성 배열 내부의 값이 변경되지 않는 이상 다시 초기화되지 않는다. 만약에 의존성 배열 내부의 값이 변경된다면 그제서야 calculate 함수는 새로 만들어진 새로운 함수로 초기화 된다.

## 3. useCallback 사용 예제

![](https://velog.velcdn.com/images/hyeun427/post/3fec521d-e4a4-4f6b-9486-3e472a866f88/image.png)

![](https://velog.velcdn.com/images/hyeun427/post/f655cbfa-52b5-4424-a17c-526569ff3bdb/image.png)

사이즈가 변경될 때만 Box 컴포넌트 내의 useEffect가 실행되게 하려면 createBoxStyle 함수를 useCallback으로 감싸주면 된다. 그리고 두번째 인자인 의존성 배열에 size를 넣어주게 되면 사이즈가 변경되지 않는 이상 memoize 된 createBoxStyle 함수를 재사용 하기 때문에 useEffect가 다시 불리지 않게 된다.

---

> 본 글은 [별코딩](https://youtu.be/XfUF9qLa3mU) 영상을 보고 작성한 글입니다!
