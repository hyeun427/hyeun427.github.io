---
title: "조건부 렌더링 Conditional-rendering"
excerpt: "조건을 주어 여러 결과를 렌더해보자"

categories: javascript
tags: [javascript, conditional-rendering]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### Conditional-rendering 이란?

조건부 렌더링이란, 특정 조건에 따라 다른 결과물을 렌더링 하는 것을 의미한다.

### Conditional-rendering의 종류

1. **삼항 연산자**
   문법 : data가 참이면 ? 뒤 조건 실행, 거짓이면 : 뒤 조건 실행

   ```jsx
   data ? data.fetchProfile : undefined;
   ```

2. **&& 연산자**
   문법 : data가 참이면 && 뒤 조건 실행, 거짓이면 data 실행

   ```jsx
   data && data.fetchProfile;
   ```

3. **옵셔널 체이닝**
   문법 : data가 참이면 ?? 뒤 조건 실행, 거짓이면 data 실행

   ```jsx
   data ?? data.fetchProfile;
   ```

4. **|| 연산자**
   문법 : data가 거짓이면 || 뒤 조건 실행, 참이면 data 실행

   ```jsx
   data || data.fetchProfile;
   ```

---

5. **nullish-coalescing**
   문법 : data가 거짓 중에서 null이거나 undefined이면 뒤 실행, 그 외 모든건 data 실행

   ```jsx
   data ?? data.fetchProfile;
   ```

   많이 쓰이지는 않지만 알고는 있을 것.
