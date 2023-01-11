---
title: "Async-Await"
excerpt: "async/await를 활용하는 법을 알아보자"

categories: javascript
tags: [javascript, network, async, await]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## 1. 동기 실행과 비동기 실행

Async-Await를 정리하기에 앞서서 동기실행과 비동기실행에 대해 개념을 먼저 잡고 가야한다.

> ### 동기 (Synchronous)
>
> 동기는 서버 컴퓨터의 작업이 끝날 때까지 기다린 후 다음 작업을 실행하는 방식이다.

> ### 비동기 (Asynchronous)
>
> 비동기는 서버 컴퓨터의 작업이 끝날 때까지 기다리지 않고 서버에 요청이 저장될 때까지 다른 작업을 진행한다.

동기와 비동기는 상황에 따라 장단점이 있다.
동기 방식은 직관적이지만 결과가 나올 때까지 대기해야하는 단점이 있다.
비동기 방식은 동기보다 복잡하고 시간이 걸리더라도 그 시간동안 다른 작업을 할 수 있어서 효율적으로 사용할 수 있는 장점이 있다.

## 2. Async-Await

Async/Await는 비동기를 동기로 바꿔주는 명령어이다. await 해주기 위해서는 꼭 async가 함께 쓰여야한다. 항상 붙어다니니까 잊지않도록 하자.

```
//비동기 통신
function 함수이름() {
	const data = axios.get(홈페이지 주소)
    console.log(data)
}
```

```
//동기 통신
async function 함수이름(){
	const data = await.axios.get(홈페이지 주소)
	console.log(data)
}
```

비동기 코드에 async와 await를 추가하면서 동기 통신으로 바뀌었다!

개념이 어렵지 않으니까 익숙해지도록 실습을 많이 해보도록 하자.
