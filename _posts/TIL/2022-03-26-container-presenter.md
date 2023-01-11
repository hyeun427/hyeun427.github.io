---
title: "container-presenter"
excerpt: "폴더 구조를 나눠보자"

categories: react
tags: [react, import, export]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## 실무용 폴더구조

실무에서 사용하는 폴더 구조는 여러가지 방법이 존재하고 이를 패턴이라고 부른다.
그 중 Container - Presenter에 대해 정리하고자 한다.

## Container - Presenter

Container/Presentational패턴이란, 코드를 JS와 JSX기능으로 나누는 방법이다.
JS 부분은 container, JSX부분은 Presentational 부분이다.

1. **Container - Presenter로 파일 나누기**
   ![](https://images.velog.io/images/hyeun427/post/7d0f0a20-5697-41bc-93dd-83ede0ea3357/%ED%8F%B4%EB%8D%94%EA%B5%AC%EC%A1%B0.png)

2. **나눈 파일을 어떻게 합칠 것 인가!?**

   1. Presenter파일을 Container에 import하면 된다

   > **부모 컴포넌트와 자식 컴포넌트**

   ✔️import되어 불려가는 컴포넌트를 자식 컴포넌트라고 한다.
   반면 import하여 불러오는 컴포넌트를 부모 컴포넌트라고 한다.
   즉, Container는 부모컴포넌트, Presenter는 자식컴포넌트이다.

   > ![](https://images.velog.io/images/hyeun427/post/11b3067b-100c-4923-862d-b3264ff17724/2.png)

   b. 그렇다면 부모⇒자식으로 값을 어떻게 넘겨줄 것인가?

   → 객체로 넘겨줄 수 있다!

   ![](https://images.velog.io/images/hyeun427/post/12f1ac43-b378-4410-a2b0-38116ce4a093/2b.png)

   1번처럼 쓰면 자동으로 2번처럼 객체가 만들어진다. Presenter에서 props를 불러오면 객체로 들어가는것!

   ![](https://images.velog.io/images/hyeun427/post/03cc2a6b-9b46-4e9b-a877-380184d6485a/2b3.png)

   여기서!!Props란 부모컴포넌트가 자식컴포넌트에게 물려주는 변수 혹은 함수라고 한다.

   \*자식이 부모에게 주는 방법 ⇒ 없음!

   \*즉, **리액트에서는 데이터의 흐름이 단방향이다. 부모⇒자식**

   Presenter와 emotion파일의 관계는 Presenter가 부모, emotion이 자식관계로 볼 수 있다
