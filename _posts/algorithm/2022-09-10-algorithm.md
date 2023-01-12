---
title: "[algorithm] 평균 구하기"
excerpt: "프로그래머스 level 1"

categories: algorithm
tags: [algorithm]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# 평균 구하기

<br/>

## 문제 설명

정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

## 제한사항

- arr은 길이 1 이상, 100 이하인 배열입니다.
- arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

---

## 입출력 예

|     arr      | return |
| :----------: | :----: |
| [1, 2, 3, 4] |  2.5   |
|    [5, 5]    |   5    |

---

## 🐤 내 답안

<details>
<summary>코드 보기</summary>
<div markdown="1">

```js
let sum = 0;

function solution(arr) {
  for (i = 0; i < arr.length; i++) {
    sum = sum + arr[i];
  }
  const answer = sum / arr.length;
  return answer;
}
```

</div>
</details>

---

> 프로그래머스의 level1 문제입니다.<br />
> 코딩테스트 연습 -> 연습문제
