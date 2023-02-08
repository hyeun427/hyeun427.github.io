---
title: "[에러기록] 크롬 SameSite 에러"
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

![](https://velog.velcdn.com/images/hyeun427/post/a4048df8-4edc-4f72-b13e-23cb98aaefd5/image.png)

- 중고마켓 포트폴리오 작업 중 로그인을 하면 작동은 잘 되지만, 개발자 도구에는 에러가 나옴.
- 에러를 찾아보니 크롬 에러.쿠키가 위험하다는 내용.
  <br>

---

<br>

### 에러 해결

![](https://velog.velcdn.com/images/hyeun427/post/2e364c0e-b289-42e6-9a98-ff6ec684dbae/image.png)

- [에러해결을 위해 이 블로그](https://wookidocs.tistory.com/m/63)를 보고 SameSite default값을 Lax로 주었더니 에러는 사라졌다...
- 하지만 에러와 해결 방법이 이해는 되지 않았다. 증상만 사라진 것 뿐........
