---
title: "[algorithm] 제일 작은 수 제거하기"
excerpt: "프로그래머스 level 1"

categories: algorithm
tags: [algorithm]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# 제일 작은 수 제거하기

<br/>

## 문제 설명

정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.

## 제한사항

- arr은 길이 1 이상인 배열입니다.
- 인덱스 i, j에 대해 i ≠ j이면 arr[i] ≠ arr[j] 입니다.

---

## 입출력 예

| arr       | return  |
| :-------- | :-----: |
| [4,3,2,1] | [4,3,2] |
| [10]      |  [-1]   |

---

## 🐤 내 답안

<details>
<summary>코드 보기</summary>
<div markdown="1">

```js
function solution(arr) {
  const min = Math.min(...arr);

  const answer = arr.filter((num) => {
    return num !== min;
  });

  return answer.length === 0 ? [-1] : answer;
}
```

</div>
</details>

---

> 프로그래머스의 level1 문제입니다.<br />
> 코딩테스트 연습 -> 연습문제
