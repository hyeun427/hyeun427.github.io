---
title: "[에러기록] React-quill을 import했는데 서버에러가 떠!"
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

- React-hook-form 안에 에디터를 사용하고 싶어서 react-quill을 넣은 상황.
- react-quill의 DOCS대로 yarn add도 잘했고, import도 react-quill과 css 둘다 했음.
- yarn dev했더니 sever Error가 나옴.

<p align=center><img src="https://velog.velcdn.com/images/hyeun427/post/b8f7f6fa-ecb3-40eb-8e01-5105d9394e95/image.png" width=800px></p>

---

### 에러 해결

```jsx
import dynamic from "next/dynamic";
```

- Quill은 ssr 지원이 되지 않기 때문에 Dynamic Import 를 사용하면, 런타임시에 필요한 module 을 import 할 수 있다.

- {ssr : false}로 세팅하고, 로드되는 동안의 상태를 렌더링할 수 있든 loading 함수도 설정할 수 있다. 아래와 같이 작성하여 만든 quill 컴포넌트를 원하는 페이지에 임포트해서 사용하면 된다.

```jsx
const QuillWrapper = dynamic(import("react-quill"), {
  ssr: false,
  loading: () => <p>Loading ...</p>,
});
```

<br>

---

<br>

[참고](https://m.blog.naver.com/choirj91/222044740530)
