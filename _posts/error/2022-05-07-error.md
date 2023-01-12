---
title: "[에러기록] Parsing error: Cannot find module 'next/babel'"
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

- 새 프로젝트 진행하려고 하는데 갑자기 import, export에 Parsing error가 뜸.
  ![](https://velog.velcdn.com/images/hyeun427/post/b17b446b-0721-42dd-bb42-dc91119bbe2e/image.png)

<br>

### 에러 해결

1. 우선 프로젝트 루트 경로에 .babelrc 파일을 생성한다.

2. .babelrc 파일에 다음 코드를 작성한다.

```jsx
{
  "presets": ["next/babel"],
  "plugins": []
}
```

3. 루트 경로에 있는 .eslintrc.json 파일을 열어 코드를 아래와 같이 수정해준다.

```jsx
{
  "extends": ["next/babel","next/core-web-vitals"]
}
```
