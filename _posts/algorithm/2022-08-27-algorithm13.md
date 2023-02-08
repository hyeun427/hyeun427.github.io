---
title: "[algorithm] 자연수 뒤집어 배열로 만들기"
excerpt: "프로그래머스 level 1"

categories: algorithm
tags: [algorithm]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# 자연수 뒤집어 배열로 만들기

<br/>

## 문제 설명

자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

## 제한사항

- `n`은 10,000,000,000이하인 자연수입니다.

---

## 입출력 예

| n     |   return    |
| :---- | :---------: |
| 12345 | [5,4,3,2,1] |

---

## 🐤 내 답안

<details>
<summary>코드 보기</summary>
<div markdown="1">

```js
function solution(n) {
  const answer = [];
  n = String(n);

  for (let i = n.length - 1; i >= 0; i--) {
    answer.push(Number(n[i]));
  }
  return answer;
}
```

</div>
</details>

---

> 프로그래머스의 level1 문제입니다.<br />
> 코딩테스트 연습 -> 연습문제
