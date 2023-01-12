---
title: "[algorithm] 가운데 글자 가져오기"
excerpt: "프로그래머스 level 1"

categories: algorithm
tags: [algorithm]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# 가운데 글자 가져오기

<br/>

## 문제 설명

단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

## 제한사항

- s는 길이가 1 이상, 100이하인 스트링입니다.

---

## 입출력 예

|    s    | return |
| :-----: | :----: |
| "abcde" |  "c"   |
| "qwer"  |  "we"  |

---

## 🐤 내 답안

<details>
<summary>코드 보기</summary>
<div markdown="1">

```js
function solution(s) {
  var answer = s;
  if (answer.length % 2 == 0) {
    const even = answer.length / 2;
    return answer[even - 1] + answer[even];
  } else {
    const odd = parseInt(answer.length / 2);
    return answer[odd];
  }
}
```

</div>
</details>

---

> 프로그래머스의 level1 문제입니다.<br />
> 코딩테스트 연습 -> 연습문제
