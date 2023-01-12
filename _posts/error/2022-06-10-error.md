---
title: "[에러기록] 로그인을 하면 헤더에 적용이 선택적이다!"
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

- 포트폴리오 작업 중 헤더에 데이터가 선택적으로 들어간다.
- 도대체 어느 기준으로 데이터가 들어갔다가 안들어갔다가 하는 건지 찾아보았다.
- const { data } = useQuery

fetch가 되었다가 안되었다가 해서 화가난다아아아앙

![](https://velog.velcdn.com/images/hyeun427/post/ac9a06f0-237e-44e3-8558-642c8be61803/image.png)

### 에러 해결

- 쿼리를 작성하는 곳에 받아오지 않는 데이터 값을 적어주어서 에러가 발생했던 것!
- 필요한 데이터만 적어주자!
