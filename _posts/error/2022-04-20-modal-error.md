---
title: "[에러기록] 모달이 팝업으로 뜨지 않아!"
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

- antd에서 modal을 import해서 적용시켰는데 브라우저에서 모달이 기대한대로 팝업처럼 뜨지않고 화면 맨 아래에 나오는 상황. 또, ok를 눌러도 사라지지 않는 문제가 발생.

<p align =center><img src="https://velog.velcdn.com/images/hyeun427/post/77c91b0a-24ce-40b5-951a-bf42f9c2a06f/image.png" height=100px></p>

---

### 에러 해결

- 모달에 적용할 CSS도 import를 해주어야한다!
- 잘 모르겠을 때는 라이브러리의 DOC를 읽어보는 습관을 기르자!

```jsx
//	antd의 css import하기

import "antd/dist/antd.css";
```

<p align =center><img src="https://velog.velcdn.com/images/hyeun427/post/e8eb7a43-1476-4c16-966b-45e399176d65/image.png" height=50px></p>
