---
title: "lifecycle"
excerpt: "생명주기란 무엇일까"

categories: react
tags: [react, lifecycle]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## State

State와 Props의 개념은 비슷하지만 다르다. 앞서 두 개념에 대해 간단히 정리([Props와 State 개념](https://velog.io/@hyeun427/React-props%EC%99%80-state))해놓았다.

다시 한번 간단히 정리하자면 각 컴포넌트는 상위에서 하위 컴포넌트로 값을 전달하여 사용할 수 있는데, 이 때 이 전달되는 값을 props라고 한고, state는 각 컴포넌트가 가지고 있는 개별적인 상태값이다.

이 둘의 다른 점은 **변경 가능 유무**이다.

- props는 부모 구성요소에서 설정한 정보를 포함하며 변경할 수 없는 불변성의 특징이 있다.

- state는 구성요소가 자체적으로 정보를 가지며, setState를 통해 변경이 가능하다.

## Lifecycle

생명주기는 리액트 컴포넌트가 실행되었다가 끝나는 과정을 의미한다.

이 생명주기는 Class Component에서만 해당한다. function 컴포넌트는 생명주기가 없다.

생명주기의 단계는 아래의 이미지를 통해 확인 할 수 있다.
![생명주기 단계](https://media.vlpt.us/images/hyeun427/post/c3652a9f-5c2a-42e9-9c61-5db3877406b5/lifecycle.png)_이미지 출처: https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/_

위 이미지에 있는 componentDidMount와 componentDidUpdate, componenWillUnmount는 생명주기 메서드이다. 생명주기 메서드는 컴포넌트가 브라우저상에 나타나고, 업데이트되고, 사라지게 될 때 호출되는 메서드들이다. 컴포넌트에서 에러가 났을 때 호출되는 메서드도 있다. 이런 생명주기 메서드는 **클래스형 컴포넌트**에서만 사용할 수 있다!!
몇 가지의 생명주기 메서드를 알아보자.

먼저 componentDidMount는 마운트 될 때 발생한다. 이 메서드는 첫 렌더링이 마치고 나서 호출되는 메서드이다. 우리가 만든 컴포넌트가 화면에 나타날 때 이 메서드가 호출된다.

두 번째로, 업데이트가 되는 시점에는 render, componentDidUpdate가 호출된다. componentDidUpdate는 리렌더링이 끝나고 화면에 우리가 원하는 변화가 모두 반영되고 난 뒤에 호출되는 메서드이다. 물론, 마운트될 때, 업데이트 될 때 사용할 수 있는 메서드는 작성한 메서드 외에도 존재한다.

세 번째로 컴포넌트가 화면에서 사라지는 것을 의미하는 언마운트 메서드이다. 언마운트 메서드는 componentWillUnmount로 유일하다. componentWillUnmount는 컴포넌트가 화면에서 사라지기 직전에 호출된다.
