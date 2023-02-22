---
title: "[mydocs] Next/Router 정리"
excerpt: "Next/Router 사용법"

categories: mydocs
tags: [next, react, router]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

Next/Router 사용법을 정리해보자!!
<br>

Next.js는 라우팅 기능을 내장하고 있어서 쉽게 페이지 구성을 할 수 있다. 오늘은 구성 방법과 많이 사용하는 메서드를 정리해보려한다!

## 1. 라우트 구성

일반적인 라우트, 중첩 라우트, 동적 라우트로 구성 할 수 있다,

### 1) 일반적인 라우트

- pages/board.js -> /board
- pages/board/index.js -> /board
- pages/index.js -> /

### 2) 중첩 라우트

- pages/board/free/index.js -> /board/free
- pages/board/community/write.js -> /board/community/write
- pages/board/community.js -> /board/community

### 3) 동적 라우트

- pages/board/[menu]/index.js -> /board/:menu
- pages/board/[menu]/all.js -> /board/:menu/all
- pages/board/[..id].js -> /board/\*
- pages/board/[id].js -> /board/:id

## 2. 메서드

라우터 사용 시에 자주 사용하는 메서드는 `router.push`, `router.replace`, `router.prefetch`, `router.beforePopState`, `router.back`, `router.reload`, `router.events` 등이 있다.
그 중 `router.push`, `router.replace`, `router.back`을 정리해보려한다! 자세한 설명은 [공식 문서](https://nextjs.org/docs/api-reference/next/router)를 확인하자!

### 2-1. router.push

router.push는 라우터 히스토리 스택에 새로운 url을 쌓아준다.
예를 들어 home > login > item 순으로 페이지를 이동했을 때, router.push를 사용해 'mypage'로 이동한다면 라우터 히스토리 스택에는 home > login > item > mypage가 쌓인다. 마지막 페이지에서 뒤로가기를 누르면 'item' 페이지로 되돌아간다.

사용법.

```js
router.push(url, as, options);
```

1. url (필수✔)

- 이동할 url > url 객체 사용 가능

2. as (선택)

- 이동 후 브라우저에 표시될 URL

3. option (선택)

- scroll, shallow, locale 등의 옵션이 있다.
  {
  scroll: `default: true` 탐색 후 페이지 맨 위로 스크롤 제어
  shallow: `default: false`
  getStaticProps, getServerSideProps, getInitialProps를 다시 실행하지 않고 현재 페이지 경로 업데이트
  locale: 새로운 페이지의 locale
  }

### 2-2. router.replace

router.push와 비슷하게 동작하지만, 라우터 히스토리 스택에 새로운 url을 추가하지 않는다. 대신 기존에 있던 현재 페이지 route를 새로운 url로 대체한다.
예를 들어, home > login > item 순으로 페이지를 이동했을 때, router.replace를 사용해 'mypage'로 이동한다면 라우터 히스토리 스택에는 현재 페이지인 item이 mypage로 대체된다. 즉, home > login > mypage가 쌓인다. 마지막 페이지에서 뒤로가기를 누르면 'login' 페이지로 되돌아간다.

사용법.

```js
router.replace(url, as, options);
```

1. url (필수✔)

- 이동할 url > url 객체 사용 가능

2. as (선택)

- 이동 후 브라우저에 표시될 URL

3. option (선택)

- scroll, shallow, locale 등의 옵션이 있다.
  {
  scroll: `default: true` 탐색 후 페이지 맨 위로 스크롤 제어
  shallow: `default: false`
  getStaticProps, getServerSideProps, getInitialProps를 다시 실행하지 않고 현재 페이지 경로 업데이트
  locale: 새로운 페이지의 locale
  }

### 2-3. router.back

히스토리에서 전단계로 이동한다. 브라우저의 뒤로가기 버튼을 누르는 것과 동일하게 작동한다.
사용법.

```js
router.back();
```

---

[참고](https://nextjs.org/docs/api-reference/next/router)
[참고](https://velog.io/@gwak2837/React-Router-History-push%EC%99%80-replace%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90)
