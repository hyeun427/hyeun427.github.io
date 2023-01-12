---
title: "[mydocs] apollo-client로 graphql 뮤테이션 실행하는 방법"
excerpt: "뮤테이션 실행 헷갈려!"

categories: mydocs
tags: [apollo client, graphql, mutation]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### apollo-client로 graphql 뮤테이션 실행하는 방법

<br>

1. apollo-client가 설치되었는지 \_app.js에 들어가서 확인한다.
   - uri에 연결할 백엔드 주소를 넣어준다!

<p align=center><img src="https://velog.velcdn.com/cloudflare/hyeun427/6a8a1d53-974a-46a4-aeaa-c3b07c1f3621/image.png" width=600px></p>
<br>

2. mutation을 사용하기 전, playground에서 우리가 사용하려는 mutation이 제대로 작동하는지 확인한다.

<p align=center><img src="https://velog.velcdn.com/cloudflare/hyeun427/ffd12d21-4d9b-4f0e-9ed5-c3afa6ba69b7/image.png" height=300px></p>

<br>
3. 제대로 작동한다면 mutation을 실행하려는 페이지 상단에 apollo-client의 도구들을 불러온다.

```
import { useMutation, gql } from '@apollo/client'
```

</br>
4. javascript 입력 부분에 playground의 코드를 복사하여 아래와 같이 gql`` 사이에 붙여넣어 변수/상수를 만들어준다.

✔️아래의 CREATE_BOARD를 대문자로 만든 것은 관례

```jsx
// graphql 코드 생성
const CREATE_BOARD = gql`
  mutation {
    createBoard(
      writer: "훈이"
      password: "1234"
      title: "안녕하세요 훈이에요"
      contents: "반갑습니다"
    ) {
      message
    }
  }
`;
```

🐣CREATE_BOARD라는 이름의 변수에 createBoard라는 뮤테이션을 넣어준거야!

</br>

5. 위에서 만든 gql 변수/상수를 활용하여, useMutation을 만들어준다.

```jsx
// mutation 코드 생성
const [createBoard] = useMutation(CREATE_BOARD);
```

(createBoard는 mutation을 실행하기 위한 이름이다. 아무 이름을 붙여도 괜찮다)

</br>

6. 게시물 등록 버튼을 클릭했을 때 실행되는 함수에서 mutation 코드를 실행해준다.

```jsx
function handleClickPost() {
  createBoard({
    variables: {
      aaa: "훈이",
      bbb: "1234",
      ccc: "안녕하세요 훈이에요",
      ddd: "반갑습니다",
    },
  });
  return <button onClick={handleClickPost}>게시물 등록</button>;
}
```

🐣 variables는 형식!왜 variables를 적었지?라는 고민은 이제 그만!

<br>

7. 게시물이 정상적으로 등록되는지 확인한다.

---

📢하지만 위의 코드는 항상 같은 게시물이 등록된다. 동적인 값을 받아오고, 주려면 CREATE_BOARD의 일부분이 변경되어야한다. 이 때 사용하는 것이 $. $를 바뀌는 값 앞에 작성하면 '이 값은 바뀌는 값이야'라는 의미!

변경 된 코드를 확인해보자!

<img src="https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F0e2279ea-5c67-498b-b46a-6890b8b27cdf%2FUntitled.png?table=block&id=032fae94-6e9b-4d74-8af1-62d9d0a3776c&spaceId=9c9b02bc-6cb6-4924-bf38-dad25e0fe77b&width=2000&userId=0380f88f-2d2e-4792-b782-40c80b1e92df&cache=v2">

이렇게 해도 계속 똑같은 데이터만 들어가게 되는데, 들어가는 데이터를 고정된 값 대신 **state**로 변경하면 완성!!

---

### 🐣**playground 보는 법!**

<p align=center><img src="https://velog.velcdn.com/cloudflare/hyeun427/9f457231-3d7d-4a65-b873-288c0ddae462/image.png" height=100px></p>

---

### 🐣실제 내 포트폴리오 코드에서 데이터의 흐름을 파악해보자!

![](https://velog.velcdn.com/cloudflare/hyeun427/3dc21fd3-8328-42ad-acef-a8096bfdf3d7/image.png)

![](https://velog.velcdn.com/cloudflare/hyeun427/41b09c3b-e2ab-4636-910e-5f6543d30aeb/image.png)

1번에서 우리가 사용자에게 요청할 값들을 작성해주고,

그 값들이 제대로 들어간다면 2번으로 이동하여 타입을 확인해준다. 모두 정상적으로 확인이 된다면 3번으로 진행된다.

우리가 사용자에게 받아온 값들을 백엔드에서 넘겨준 createBoard에 넣어준다.

그리고 제대로 다 넣어줬다면 우리는 백엔드에서 그 게시글의 id값을 받아올 것이다.(\_id만 요청했으므로)

그렇다면 받아온 id값은 어디에서 확인할 수 있는가? 5번을 따라가면 된다.

result.data.\_id가 아니라 result.data.createBoard.\_id인 이유는 console.log(data)를 찍어보면 확인 할 수 있다.

백엔드에서 data라는 객체안에 createBoard라는 객체안에 \_id와 다른 data값들을 넣어줬기때문에 result.data.createBoard.\_id로 받아와야 하는 것!

백엔드에서 어떻게 넘겨줄지 모르기때문에 코드작업을 할 때 항상 console.log로 찍어보고 확인하는 습관을 기르자.

저 보라색 createBoard는 무엇인가?createBoard의 뮤테이션을 CREATE_BOARD에 담아줬고 그 CREATE_BOARD가 실행하는 변수명이 createBoard인 것이다. 헷갈리지 말 것!
