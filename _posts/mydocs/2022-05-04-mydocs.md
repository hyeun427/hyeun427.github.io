---
title: "[mydocs] 배경화면 이미지 꽉 채우기"
excerpt: "꽉 채워줘!"

categories: mydocs
tags: [css]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 페이지에 배경화면 이미지 꽉차게 채우기

- background-size를 cover로 설정하기
- background-position: center;가 없을 때는 이미지가 꽉차긴 하지만 원하는 이미지 전체가 보여지지 않고 화면 크기에 맞게 잘렸었음
- 아래 코드를 다 작성하니까 반응형으로 이미지가 잘리지 않고 원하는대로 보여짐

```jsx
body {
        background-image: url('#');
  		background-size: cover;
  		background-position: center;
  		background-repeat: no-repeat;
  		width: 100vw;
  		height: 100vh;
      }
```

<br>

---
