---
title: "[에러기록] 크롬 콘솔 에러:Unchecked runtime.lastError:The message port closed before a response was received."
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

- 에러 메세지 : `Unchecked runtime.lastError:The message port closed before a response was received.`
- 개인 프로젝트 진행 중 다른 브라우저에서는 콘솔 창에 에러 메세지가 나오지 않았는데, 크롬에서만 에러 메세지가 출력되는 상황을 경험

![크롬 콘솔 에러](/assets/images/error/23021001.PNG)

---

### 에러 해결

- 처음 보는 에러여서 구글링을 했고, 그 결과 크롬 확장 프로그램과 충돌이 발생해서 에러 메세지가 출력되었다는 사실을 알게 되었다.
- 해결책으로는 내가 활성화한 확장 프로그램을 하나씩 비활성화하면서 프로젝트 화면을 새로고침하면서 콘솔창을 확인하였다
- 나의 경우, 유튜브 빨리감기를 위한 확장 프로그램이 충돌을 일으키는 것을 확인 할 수 있었다!

![확장 프로그램 비활성화](/assets/images/error/23021002.PNG)
