---
title: "자바스크립트에서 작성한 대로 출력하고 싶을땐?!"
excerpt: "template literals을 사용해 white-space를 그대로 적용해보자."

categories: javascript
tags: [javascript, template literals]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## Template literals

---

템플릿 리터럴은 내장된 표현식을 허용하는 문자열 리터럴이다. ES2015 사양명세서에선 template strings라고 불렸다. 템플릿 리터럴은 백틱 ( ) 문자를 사용하고, 표현식/문자열 삽입, 여러 줄 문자열, 문자열 형식화, 문자열 태깅 등 다양한 기능을 제공한다.

ES6 이전과 템플릿 리터럴의 사용 예시를 통해 편리함을 더욱 느낄 수 있다

- 이전 사용 예시

```
let a = 1327;
let b = "프론트엔드 6기 짱구";
let c = "저는 " + a + "호실에서 공부하는 " + b + "입니다.";
console.log(c);   //저는 1327호실에서 공부하는 프론트엔드 6기 짱구입니다.

```

- 템플릿 리터럴 사용 예시

```
let a = 1327;
let b = "프론트엔드 6기 짱구";
let c = `저는 $(a)호실에서 공부하는 ${b}입니다.`;
console.log(c);   //저는 1327호실에서 공부하는 프론트엔드 6기 짱구입니다.
```

템플릿 리터럴은 일반적인 문자열과 달리 띄어쓰기, 줄바꿈 등 작성한 문자열 그대로 적용한다..

주의할 점은 백틱 문자를 작은 따옴표와 헷갈리지 않기!
