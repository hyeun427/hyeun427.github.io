---
title: "Token, XSS, CSRF"
excerpt: "유저를 구별하자!"

categories: network
tags: [network, Token, XSS, CSRF]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## Token

토큰이란 서버에 접속한 유저가 누구인지 구별할 수 있도록 브라우저에 사용자 정보를 저장해 놓은 것이다. 권한분기를 위해서 유저를 구별해야 하기때문에 필요하다.사용자 정보를 암호화해서 브라우저에 저장하고, 웹페이지 접속 시, 저장된 정보를 가져와서 사용자마다 다른 화면을 보여줄 수 있다.

<br><br>

## XSS (Cross-Site Scripting)

<p align=center><img src="https://blog.kakaocdn.net/dn/A9Jd6/btqAtCjHGoU/3Bal6vUNOLs3hlVd3zAc2K/img.gif" width=500px/></p>

XSS는 <span style="color:red">**악의적인 사용자가 공격하려는 사이트에 스크립트를 넣는 기법**</span>으로 다른 웹사이트와 정보를 교환하는 방식으로 작동하므로 <span style="color:red">**사이트 간 스크립팅**</span>이라고 한다. 주로 게시판에 악성 스크립트가 담긴 글을 올리는 형태로 이루어지고, 그 글을 클릭하는 사용자의 쿠키나 세션 토큰 등의 민감한 정보를 탈취해간다.

<br><br>

## CSRF (Cross-Site Request Fogery)

<p align=center><img src="https://velog.velcdn.com/images/hyeun427/post/24631684-78ba-4555-b007-d34abdd01ce7/image.png" width=500px/></p>

CSRF는 <span style="color:red">**사용자가 자신의 의지와는 무관하게 공격자가 의도한 행위(수정, 삭제, 등록 등)를 특정 웹사이트에 요청하게 하는 공격**</span>을 의미한다.

CSRF공격이 성공하려면 아래의 두가지 조건을 만족해야한다.

1. 위조 요청을 전송하는 서비스(ex : 페이스북)에 희생자가 로그인 상태여야함.
2. 희생자는 공격자가 만든 피싱 사이트에 접속해야함.

<br>
<br>

---

[Reference1](https://lucete1230-cyberpolice.tistory.com/23) , [Reference2](https://program-developer.tistory.com/99)
