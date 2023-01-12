---
title: "[mydocs] 랜딩페이지 레이아웃 숨기기"
excerpt: "레이아웃을 숨겨보자"

categories: mydocs
tags: [landing page, layout]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 랜딩페이지 레이아웃 숨기기

- 랜딩페이지의 asPath 값을 확인
  <br>
- 레이아웃 index파일에 랜딩페이지의 주소를 변수에 넣어주기

 <img src="https://velog.velcdn.com/cloudflare/hyeun427/2c900058-722e-49e2-8ea2-c5d987d1f93a/image.png" width=500px>
<br>
- includes() 를 사용해 배열내 값과 현재 페이지의 asPath의 값을 비교하여 동일하지 않을 경우에만 레이아웃 화면을 출력해주면 페이지에 따라 화면을 달리 구성하면 된다
    
 <img src="https://velog.velcdn.com/cloudflare/hyeun427/ef90f267-ae3b-417e-95db-84181dde80f2/image.png" width=500px>

 <img src="https://velog.velcdn.com/cloudflare/hyeun427/c4f35bbe-dbb9-416c-8e66-30e99d3287d8/image.png" width=500px>

<br>

---

<br>

### 🐣 블로그 작성하면서 생긴 의문점

router를 사용해서 굳이 비교를 해야하나? return에 asPath값을 넣은 HIDDEN_LAYOUT을 바로 넣어서 삼항연산자로 비교해서 구성하면 되지 않을까? 라는 생각이 들었다. 그래서 코드를 작성해 실행 시켜보았다.

<img src="https://velog.velcdn.com/cloudflare/hyeun427/4718cb1c-76a0-4f75-a71e-a864fe3c8245/image.png" width=500px>

yarn dev를 해서 화면을 확인해보니 동일하다! 그렇다면 왜 내가 한 것처럼 바로 넣지않고 router로 비교를 하는 걸까 더 고민해보았다.

결론부터 말하면 직접 비교한 코드가 동일하게 실행된 이유는 레이아웃을 제외시킬 페이지가 우연히 1개였기때문이다. 만약 1개가 아니라 여러 페이지가 있다면 HIDDEN_LAYOUT 배열의 인덱스가 여러 개 일 것이고, 이 상황에서 내가 한 것 처럼 직접 비교하면 인덱스 값을 모두 확인해야하기때문에 정말 비효율적이다. icludes로 확인해서 나온 불린 값으로 코드를 돌린다면 훨씬 효율적이다.

의문점 해결😄
