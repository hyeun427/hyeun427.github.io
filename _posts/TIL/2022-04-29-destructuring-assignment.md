---
title: "구조분해할당"
excerpt: "커링 넌 도대체 뭐니"

categories: javascript
tags: [javascript, destructuring assignment]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

구조분해할당 기초 이해하기

#### 예시1

```jsx
const profile = {
  name: "철수",
  age: 8,
  school: "다람쥐초등학교",
};
// 1. 새 변수에 profile 객체의 name의 키와 value를 직접 할당해줌.
const name = profile.name;
name; // '철수'

// 2. 구조분해할당
const { age, school } = profile;
age; // 8
school; // '다람쥐초등학교'
```

> 1번에서는 name이라는 새로운 변수에 profile.name을 직접 할당해주었고
> 2번에서는 구조분해할당을 이용하였다.
> 1번 방식으로 할당을 하게 되면 name, age, school을 할당하는 코드가 3줄이 나올텐데,
> 구조분해할당(2번)을 이용하면 중괄호 안에 다 넣으면 되기때문에 한줄로 끝난다!

---

#### 예시2

```jsx
function useQuery(aaa) {
  return {
    data: {
      fetchBoard: {
        writer: "철수",
        title: "제목",
        contents: "내용",
      },
    },
    loading: "로딩중!",
  };
}

useQuery("FETCH_BOARD"); // {data: {…}, loading: '로딩중!'}data: {fetchBoard: {…}}loading: "로딩중!"[[Prototype]]: Object

const { data, loading } = useQuery("FETCH_BOARD");

data; // {fetchBoard: {…}}
data.fetchBoard.writer; // '철수'
data.fetchBoard.title; // '제목'
data.fetchBoard.contents; // '내용'
loading; // '로딩중!'
```

---

#### 예시3

```jsx
const classmates = ["철수", "영희", "훈이"];

const child1 = classmates[0];
child1; // "철수"

const [, child2, child3] = classmates;
child2; // "영희"
child3; // "훈이"
```

> child1에 철수를 넣어줬으니까 영희, 훈이만 새 변수에 넣어주고 싶어!
> 그러면 철수, 영희, 훈이 순서에서 철수를 빼고 구조분해할당해주어야하니까
> 철수 부분엔 빈칸으로 두고 쉼표를 반드시 명시!!
> 그러면 나머지는 순서대로 각 변수에 할당됌!

---

#### 예시4

```jsx
function useState(aaa) {
  const myState = aaa; // 초기값으로 사용
  const setMyState = (bbb) => {
    console.log(`state를 ${bbb}로 바꿔줄게!~`);
  };
  return [myState, setMyState];
}

const [count, setCount] = useState(10);
setCount(20); // state를 20로 바꿔줄게!~

// setCount()를 qqq[1](50)형식으로도 쓸 수 있어!
const qqq = useState(30);
qqq[0]; // 30
qqq[1](50); // tate를 50로 바꿔줄게!~
```

위의 코드들을 보면서 객체일때와 배열일 때 사용법을 잘 알아두도록 하자.

---

#### 예시5

```jsx
function getChild() {
  return {
    name: "chulsu",
    age: 13,
    school: "cocamp",
  };
}

const { school } = getChild();

school; // 'cocamp'
```

---

#### 예시6. 서로 바꿔서 출력해주는 방법

```jsx
function getClassmates(aaa, bbb) {
  return [bbb, aaa];
}

const [child1, child2] = getClassmates("훈이", "맹구");

child1; // '맹구'
child2; // '훈이'
```
