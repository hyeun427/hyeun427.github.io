---
title: "observable"
excerpt: "observable은 무엇인가"

categories: RxJava
tags: [RxJava, observable]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

RxJava의 가장 핵심적인 요소인 Observable은 데이터 흐름에 맞게 알림을 보내 Observer가 데이터를 사용할 수 있도록 한다. 즉, Observable을 이용해 데이터를 회수하고 변환하는 메커니즘을 정의하고, Observer는 이를 구독해 데이터가 준비되면 이에 반응한다.

<br>

### 알림 종류

- onNext : 데이터의 발행을 알린다.
- onComplete : 모든 데이터의 발행이 완료되었음을 알리고, 이 후 모든 구독은 끝난다.
- onError : 데이터의 흐름 중에 에러가 발생했음을 알리고, Observable의 동작이 끝난다.

<br>

### Observable의 종류

- Observable : 가장 기본적인 형태, 0개~N개의 데이터 발행, BackPressure 없음
- Single : 단 1개의 데이터, 혹은 오류 발행
- Completable : 성공 혹은 실패했다는 결과만 발행
- Maybe : 0개 또는 1개 완료, 오류
- Flowable : 0개~N개의 데이터 발행, BackPressure 존재
