---
title: "rest-api와 graphql-api란 무엇인가"
excerpt: "rest와 graphql의 차이"

categories: network
tags: [network, rest-api, graphql-api]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## Rest-API

REST는 Representational State Transfer의 약자로, 모든 Resource들을 하나의 endpoint에 연결하고, 각 Endpoint는 그 Resource와 관련된 내용만 관리하게 하는 방법이다.rest-api는 응답 결과로 back-end개발자가 만든 함수에서 보내주는 모든 데이터를 받아야만 한다. rest-api에 요청하는 요청담당자는 axios이다.

## GraphQL-API

GraphQL은 Graph Query Language의 약자로, 하나의 endpoint를 사용하고, back-end개발자가 만든 함수에서 필요한 데이터만 골라 받을 수 있다. graphql-api에 요청하는 요청담당자는 apollo-client이다.

---

한 방에 정리!
![](https://images.velog.io/images/hyeun427/post/8938b0f4-1fb4-4c29-9473-60db8629ffae/api.png)
