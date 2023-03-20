---
title: "[에러기록] Warning: A component is changing an uncontrolled input to be controlled."
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

- 에러 메세지 : `Warning: A component is changing an uncontrolled input to be controlled.`
- 게시글을 수정할 때를 위해 작성한 defaultValue 코드에 경고메세지가 콘솔에 찍힘

  ![인풋 경고](/assets/images/error/23021602.PNG)

---

### 에러 해결

- 수정이 아닌 처음 작성하는 게시글에는 props로 받아오는 값이 없어서 경고가 나오는 것
- `||`을 사용해서 undefided일 때는 `""`로 처리하도록 했음

![인풋 경고 해결](/assets/images/error/23021603.PNG)
