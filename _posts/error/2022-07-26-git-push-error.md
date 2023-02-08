---
title: "[에러기록] error:failed to push some refs to ..!깃 푸쉬하고싶다고!"
excerpt: "에러 기록하기"

categories: error
tags: [error]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### 에러 상황

![](https://velog.velcdn.com/images/hyeun427/post/3e218a52-cba5-44ec-8189-0f7540843803/image.PNG)

깃 푸쉬를 시도했는데 `error:failed to push some refs to...`에러가 나왔다!
~~(부트캠프 첫 주에 만났던 에러 친구였는데 지금 보니까 별 거 아니네👓)~~

### 에러 해결

위 에러는 `github`에 내 `local`에 없는 파일이 있는데 내 파일을 `push`하려고 할 때 발생하는 오류이다.

#### 해결방법1.

`git pull`한 뒤 `git push`하면 된다.
![](https://velog.velcdn.com/images/hyeun427/post/6f9b06a3-a279-410d-849f-92a2a8b2039a/image.PNG)

만약 `pull`했는데도 `push`가 되지 않는다면?!

#### 해결방법2.

강제로 `git push`해버리자!~
명령어는 `git push -f origin main`

**협업을 하는 도중이라면 깃 문제가 커질 수 있으니 주의해야한다!!!~**
![](https://velog.velcdn.com/images/hyeun427/post/c15c38a6-8966-4606-9da1-7d4f3bc7f34d/image.PNG)
