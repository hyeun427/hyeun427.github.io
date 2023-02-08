---
title: "[에러기록] create-react-app 에러"
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

- 새로운 react 프로젝트를 만드는 과정에서 에러가 발생했다.
- 메세지에서 시킨대로 해도 에러가 해결되지 않았다.

```jsx
- npm uninstall -g create-react-app
- yarn global remove create-react-app
```

<p align =center><img src="https://velog.velcdn.com/images/hyeun427/post/3e3e930d-55f9-4660-b346-6059c402ae12/image.PNG" height=100px></p>

---

### 에러 해결

```jsx
npx create-react-app@latest <project-name>
```

`@latest`붙여서 다시 시도 하니까 해결되었다!
