---
title: "cookie, session, local storage"
excerpt: "장바구니 정보는 어디에 저장하는 걸까?"

categories: web
tags: [web, cookie, session storage, local storage]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### Cookie

- 클라이언트 하드에 저장되는 key와 value값이 들어있는 데이터 파일
- 서버에 저장되는 것이 아니라서 보안과 상관없는 정보들에 사용
- 보안에 취약하기 때문에 공공장소에서 해킹 등 악용이 가능
- 이름, 값, 만료날짜, 경로 정보가 있어야하고 일정 시간동안 데이터를 저장할 수 있음
- 같은 도메인 상에서 쿠키의 값은 공유
- 클라이언트가 요청하지 않아도 브라우저 요청이 있을 경우 Request Header에 넣어서 자동으로 서버에 전송한다.

### Session Storage

- 데이터의 만료기간은 세션이 종료되는 시점. 즉, 세션 종료시 데이터가 삭제됨
- 사이트 재 방문시 이전에 저장되었던 정보를 이용 할 수 있어 활용도가 높음
- 사용자 설정 저장, 브라우저를 닫고 열었음에도 정보가 남아야 하는 것들을 저장할 때 사용

### Local Storage

- 데이터의 만료기간이 없으며 사용자가 데이터를 지우지 않은 한 영구적으로 보존
- 사이트 재 방문시 이전에 저장되었던 정보를 이용 할 수 있어 활용도가 높음
- 사용자 설정 저장, 브라우저를 닫고 열었음에도 정보가 남아야 하는 것들을 저장할 때 사용

#### 참조

- https://okayoon.tistory.com/entry/브라우저-쿠키Cookie-세션스토리지Session-Storage-로컬스토리지Local-Storage [Zzolab Blog :)]
