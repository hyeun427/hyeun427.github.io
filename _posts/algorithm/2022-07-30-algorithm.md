---
title: "[algorithm] 자릿수 더하기"
excerpt: "프로그래머스 level 1"

categories: algorithm
tags: [algorithm]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# 자릿수 더하기

<br/>

## 문제 설명

자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.
예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

## 제한사항

- N의 범위 : 100,000,000 이하의 자연수

---

## 입출력 예

| N   | answer |
| :-- | :----- |
| 123 | 6      |
| 987 | 24     |

### 입출력 예 설명

#### 입출력 예 #1

문제의 예시와 같습니다.

#### 입출력 예 #2

9 + 8 + 7 = 24이므로 24를 return 하면 됩니다.

---

## 🐤 내 답안

<details>
<summary>코드 보기</summary>
<div markdown="1">

```javascript
function solution(n) {
  const answer = n
    .toString()
    .split("")
    .reduce((acc, cur) => {
      console.log(acc, cur);
      return acc + Number(cur);
    }, 0);
  return answer;
}
```

</div>
</details>

---

> 프로그래머스의 level1 문제입니다.<br />
> 코딩테스트 연습 -> 연습문제
