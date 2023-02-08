---
title: "[mydocs] apollo-client로 graphql 쿼리 실행하는 방법"
excerpt: "쿼리 실행 헷갈려!"

categories: mydocs
tags: [apollo client, graphql, query]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### apollo-client로 graphql 쿼리 실행하는 방법

```jsx
// graphql 요청에 필요한 도구 불러오기
import { useQuery, gql } from '@apollo/client'


// graphql 코드 생성
const FETCH_PROFILE = gql`
	query fetchProfile($name: String){
		fetchBoard(name: $name){
			title
			contents
		}
	}
`


// graphql 코드를 실행하기 위한 query 생성과 생성된 query의 실행(자동으로 실행됩니다)
const { data } = useQuery(FETCH_PROFILE)


// 최종 결과를 HTML에 보여주기
<div>
	이름: <span>{data && data.fetchProfile.name}</span>
	나이: <span>{data && data.fetchProfile.age}</span>
	학교: <span>{data && data.fetchProfile.school}</span>
</div>
```

<br>

---

<br>

### 템플릿 리터럴(Template Literal)

문자와 변수를 함께 쓸 수 있는 도구이다.
`${변수명}`으로 string과 변수를 연산자로 더해주지 않아도 가독성 좋게 코드를 작성할 수 있다.

<br>

```jsx
const first = "영희";
const last = "김";

// 문자열 연결
console.log("My name is " + first + " " + last + ".");
// 'My name is 김 영희.'
```

<br>

---

### 🐣데이터 흐름 파악하기

![](https://velog.velcdn.com/cloudflare/hyeun427/5bdac359-7a8e-41e7-8188-56d26aa07866/image.png)
