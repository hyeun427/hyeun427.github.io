---
title: "[mydocs] refetchQueries"
excerpt: "refetchQueries 정리해주마"

categories: mydocs
tags: [refetchQueries]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

refetchQuery는 useMutation의 옵션으로, 기존에 받아왔던 데이터가 변경 되었을 경우 최신 데이터로 다시 fetch 해주기 위해 사용한다.

refetchQuery는 query와 variable의 배열을 값으로 갖는다. 또 mutation과 동시에 비동기적으로 원하는 쿼리를 refetch한다.

awaitRefetchQueries 옵션을 통해 refetchQueries에 입력한 query의 동기/비동기 여부를 설정할 수도 있다.

<br>

- refetchQuery의 사용법을 알아보자.

```jsx
//refetchQueries를 이용해 최신 데이터 받아오기

const deleteBoard = async () => {
  try {
    const result = await deleteBoard({
      variables: {
        boardId: router.query.boardId,
      },
      refetchQueries: [
        {
          query: FETCH_BOARDS,
        },
      ],
    });
  } catch (error) {
    console.log(error);
  }
};
```

<br>

refetchQueries는 배열로 시작하여, 그 안에 어떤 query를 하고, 그 query의 variables가 무엇인지 다시 설정해주면 Mutation이 성공적으로 끝났을 경우 refetchQueries를 실행한다.

<br>

💡 **refetchQueries에서의 variables**
→ 기존의 fetch 부분에서 보내준 variables가 없다면 따로 적지 않아도 되지만,
만일 보내준 variables가 있다면 refetchQuerise부분을 아래와 같이 적어야한다!

```jsx
refetchQueries: [
	           {
		     query : FETCH_BOARDS,
                     variables : { 기존의 fetch때 보내준 것 }
		     },
		]
```
