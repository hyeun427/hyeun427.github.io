---
title: "@media , Responsive Design"
excerpt: "반응형 디자인 한번 해볼래?"

categories: css
tags: [css, media, responsive design]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## 반응형 디자인

반응형 디자인이란 디바이스(전자기기)별로 각각 레이아웃(grid)가 달라지게 하는 작업을 의미한다.

## 미디어쿼리 (Media Query)

반응형 웹에서는 필수인 미디어쿼리는, 화면크기 마다 각각 다르게 CSS를 적용하는 것이다.
화면 사이즈를 인식해 서로 다른 CSS를 적용시켜준다. 일반적으로 스마트폰, 태블릿 , PC 화면 3가지로 구분한다.

> PC : 해상도 1024px 초과
> 태블릿 : 해상도 768px 이상 또는 1024px 미만
> 스마트폰 : 해상도 320px 이상 또는 768px 미만

<br>

### 미디어 쿼리 적용 예시

미디어 쿼리 적용 예시로 이해해보자!

```jsx
.title {
  font-size: 40px;
}

@media (max-width: 768px) {
  .title {
    font-size: 20px;
  }
}
```

<br>

타이틀의 텍스트 크기를 40px로 하되, 768px보다 작은 화면에서는 20px로 줄인다는 코드이다!!

<br>

### 미디어 쿼리 적용방법

1. CSS 파일 내에 직접 작성

2. <link\> 태그에 media 속성을 설정해 사용

<br>

---

[참고1](https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Responsive_Design#%EB%B0%98%EC%9D%91%ED%98%95_%EB%94%94%EC%9E%90%EC%9D%B8)
[참고2](https://velog.io/@bungouk6829/%EB%B0%98%EC%9D%91%ED%98%95-%EC%9B%B9%EC%9D%98-%EB%AF%B8%EB%94%94%EC%96%B4-%EC%BF%BC%EB%A6%AC-Media-Query-%EC%99%80-Viewport)
