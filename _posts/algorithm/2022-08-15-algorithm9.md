---
title: "[algorithm] 문자열 다루기 기본"
excerpt: "프로그래머스 level 1"

categories: algorithm
tags: [algorithm]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# 문자열 다루기 기본

<br/>

## 문제 설명

문자열 s의 길이가 4 혹은 6이고, 숫자로만 구성돼있는지 확인해주는 함수, solution을 완성하세요. 예를 들어 s가 "a234"이면 False를 리턴하고 "1234"라면 True를 리턴하면 됩니다.

## 제한사항

- `s`는 길이 1 이상, 길이 8 이하인 문자열입니다.
- `s`는 영문 알파벳 대소문자 또는 0부터 9까지 숫자로 이루어져 있습니다.

---

## 입출력 예

| divisor | return |
| :-----: | :----: |
| "a234"  | false  |
| "1234"  |  true  |

---

## 🐤 내 답안

<details>
<summary>코드 보기</summary>
<div markdown="1">

```js
function solution(s) {
  if (s.length !== 4 && s.length !== 6) {
    return false;
  }

  const answer = s.split("").filter((num) => {
    // 데이터가 숫자가 아닌 문자일 경우만 남긴다.
    //isNaN의 결과가 true 값인 경우 (NaN 값인 경우)
    return isNaN(num) === true;
  });
  return answer.length === 0;
}
```

</div>
</details>

---

> 프로그래머스의 level1 문제입니다.<br />
> 코딩테스트 연습 -> 연습문제
