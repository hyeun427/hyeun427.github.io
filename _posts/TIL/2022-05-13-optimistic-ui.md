---
title: "optimistic-ui"
excerpt: "사용자 경험을 높이면서 작업하면 훨씬 좋지!"

categories: react
tags: [react, optimistic-ui]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## optimistic-ui

옵티미스틱UI란 단어 그대로 낙관적인 UI이다. 요청 결과를 오류가 나지 않을 것을 미리 예상해서 사용자에게 성공 시 결과를 바로 보여주는 것(실제 요청결과가 나오기 전에)이다.

이는 사용자 경험 향상을 위한 기법 중 하나로, 요청이 올 때까지 기다리는 대신 우선 UI를 변경해두고, success response가 오지 않을 경우에는 에러 처리 또는 롤백 처리를 한다.

간단한 예시를 보면서 이해해보자.

기존에 좋아요를 눌렀을 때, 화면에 출력되는 과정은 아래와 같다.

> 1. 사용자가 👍 버튼을 누릅니다.
> 2. onClick 함수가 실행되고 서버에 mutation 요청을 보내게 됩니다.
> 3. 서버에 보낸 요청이 완료될 때까지 await으로 기다립니다.
> 4. 완료됐다는 응답이 오면 이제 refetch를 해서 좋아요 갯수 데이터를 다시 가져옵니다.
> 5. 가져온 데이터를 화면에 보여줍니다.

하지만, 옵티미스틱UI로 코드를 작성하게 되면 사용자가 화면에 확인하는 시간이 더 빨라진다.

> 1. 사용자가 👍 버튼을 누릅니다.
> 2. 좋아요 갯수가 1개 증가한 UI를 바로 보여줍니다.
> 3. 서버에 mutation을 요청합니다.
> 4. 서버에서 응답을 받습니다.

[참고](https://ahnanne.tistory.com/35)
