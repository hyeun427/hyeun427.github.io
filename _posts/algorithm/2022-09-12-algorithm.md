---
title: "[algorithm] 행렬의 덧셈"
excerpt: "프로그래머스 level 1"

categories: algorithm
tags: [algorithm]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# 행렬의 덧셈

<br/>

## 문제 설명

행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요.

## 제한사항

- 행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.

---

## 입출력 예

|     arr1      |     arr2      |    return     |
| :-----------: | :-----------: | :-----------: |
| [[1,2],[2,3]] | [[3,4],[5,6]] | [[4,6],[7,9]] |
|   [[1],[2]]   |   [[3],[4]]   |   [[4],[6]]   |

---

## 🐤 내 답안

<details>
<summary>코드 보기</summary>
<div markdown="1">

```js
function solution(arr1, arr2) {
  var answer = [[]];
  for (let i = 0; i < arr1.length; i++) {
    answer[i] = [];
    for (let j = 0; j < arr1[i].length; j++) {
      answer[i].push(arr1[i][j] + arr2[i][j]);
    }
  }
  return answer;
}
```

</div>
</details>

---

> 프로그래머스의 level1 문제입니다.<br />
> 코딩테스트 연습 -> 연습문제
