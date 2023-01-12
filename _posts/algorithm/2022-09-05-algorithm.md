---
title: "[algorithm] 콜라츠 추측"
excerpt: "프로그래머스 level 1"

categories: algorithm
tags: [algorithm]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# 콜라츠 추측

<br/>

## 문제 설명

1937년 Collatz란 사람에 의해 제기된 이 추측은, 주어진 수가 1이 될 때까지 다음 작업을 반복하면, 모든 수를 1로 만들 수 있다는 추측입니다. 작업은 다음과 같습니다.

> 1-1. 입력된 수가 짝수라면 2로 나눕니다.
> 1-2. 입력된 수가 홀수라면 3을 곱하고 1을 더합니다. 2. 결과로 나온 수에 같은 작업을 1이 될 때까지 반복합니다.

## 제한사항

- 입력된 수, num은 1 이상 8,000,000 미만인 정수입니다.

---

## 입출력 예

|   n    | result |
| :----: | :----: |
|   6    |   8    |
|   16   |   4    |
| 626331 |   -1   |

---

## 🐤 내 답안

<details>
<summary>코드 보기</summary>
<div markdown="1">

```js
function solution(num) {
  // 1이 될 때까지 반복한 횟수
  let answer = 0;

  for (let i = 0; i < 500; i++) {
    if (num === 1) {
      break;
    }

    answer++;

    //num이 짝수일 때: 해당 수에 2를 곱한다.
    if (num % 2 === 0) {
      num = num / 2; // num = num / 2;
      // num이 홀수일 때: 해당 수에 3을 곱한 값에 1을 더한다.
    } else {
      num = num * 3 + 1;
    }
  }
  return num !== 1 ? -1 : answer;
}
```

</div>
</details>

---

> 프로그래머스의 level1 문제입니다.<br />
> 코딩테스트 연습 -> 연습문제
