---
title: "[mydocs] LocalStorage 쓰는게 너무 헷갈려!!"
excerpt: "LocalStorage 사용법"

categories: mydocs
tags: [local storage]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

localStorage 사용법을 정리해보자!!
<br>

## 1. 간단하게 정리해보기

- setItem() - key, value 추가
- getItem() - value 읽어 오기
- removeItem() - item 삭제
- clear() - 도메인 내의 localStorage 값 삭제
- length - 전체 item 갯수
- key() - index로 key값 찾기

<br>

## 2. setItem()으로 아이템 추가하기

```jsx
localStorage.setItem("추가 할 key명", 추가할 value)   // key에 직접 문자열을 넣고 싶을 때
localStorage.setItem(추가 할 key명, 추가할 value)	  // 값이나 식으로 바로 넣을 때
```

<p><img src='https://velog.velcdn.com/images/hyeun427/post/e4f29d81-9a40-4571-8b0e-1acdeebebebe/image.png'></p>

<br>

## 3. getItem()으로 value 읽기

```jsx
localStorage.getItem(key);
```

<p><img src='https://velog.velcdn.com/images/hyeun427/post/3ab90f36-4707-4d8b-b91b-72b9f57ec522/image.png'></p>

<br>

## 4. removeItem()으로 값 삭제하기

```jsx
localStorage.removeItem(key);
```

<p><img src='https://velog.velcdn.com/images/hyeun427/post/ff6e48f8-a240-4d01-b326-597faed45d3b/image.png'></p>

<p><img src='https://velog.velcdn.com/images/hyeun427/post/65db8c6f-916c-4df0-b297-af0e84fcff50/image.png'></p>

<br>

## 5. clear()로 도메인 내의 localStorage 값 삭제하기

```jsx
localStorage.clear();
```

<p><img src='https://velog.velcdn.com/images/hyeun427/post/156251d0-0d6c-42e6-8ca5-afe7ab2856c8/image.png'></p>

<br>

## 6. length로 전체 item 갯수 파악하기

```jsx
localStorage.length;
```

<p><img src='https://velog.velcdn.com/images/hyeun427/post/a0b8c15c-f7e9-40cd-ba04-8973d5f07317/image.png'></p>

<br>

## 7. key() - index로 key값 찾기

```jsx
localStorage.key(index);
```

<p><img src='https://velog.velcdn.com/images/hyeun427/post/c1af886b-b0bd-41cc-b0d6-c8e62a7e4619/image.png'></p>
