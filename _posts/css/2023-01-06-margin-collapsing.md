---
title: "[css] 마진 병합"
excerpt: "마진을 설정했는데 왜 제대로 적용이 안되는 것 같지..?"

categories: css
tags: [css, margin collapsing]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

# margin collapsing

## margin이란?

우선, 마진(margin)이란 요소의 네 방향 바깥 영역을 설정하는 css 속성이다.
여러 개의 요소들에 마진 값이 설정되어 있을 때 의도치않게 설정한 마진 값보다 줄어들어있거나 마진을 늘려도 늘어나지 않는 현상을 겪게 될 수 있다.
이 현상을 **마진 병합 현상**이라고 한다.

## 마진 병합 현상(margin collapsing)

마진 병합 현상은 입접하는 블록 요소의 상하단의 마진이 병합되는 현상을 말한다.
병합된 마진의 크기는 병합된 두 요소 중 큰 값의 마진 값으로 병합된다.
마진 병합은 수직 방향으로만 이루어지며, 좌우에 대해서는 일어나지 않는다.
또한 마진 병합은 _절대 위치나 상대 위치가 주어진 요소_(position, float를 지정한 경우)들에서는 발생하지 않는다.

## 마진 병합 현상이 되는 조건

### 조건1. 인접하는 블록 요소

{% include codepen.html hash="poZQWXq" title="margin" %}

box1과 box2의 마진이 각각 30px임에도 결과물을 확인해보면 두 요소의 사이 마진이 60px이 아닌 30px로 마진병합이 적용되어있는 것을 확인 할 수 있다.

### 조건2. 부모 요소와 첫번째 자식 요소 혹은 마지막 자식 요소 관계일 경우

{% include codepen.html hash="xxJmGOm" title="margin" %}

우리가 예상한 마진 형태는 'H'형태가 아닌 '8'형태이다. 하지만 마진병합으로인해서 'H'형태가 된 것을 확인 할 수 있다.

### 조건 정리

1. 인접하는 블록 요소끼리만 발생한다.
2. 부모 요소와 첫번째 자식 요소 혹은 마지막 자식 요소 관계일 경우
   - 부모 요소와 첫번째 자식 요소의 상단 마진 병합
   - 부모 요소와 마지막 자식 요소의 하단 마진 병합
3. 내용이 없는 빈 요소의 경우
   - 해당 요소의 상단 마진과 하단 마진의 병합

## 해결 방법

그렇다면 마진 병합을 해결할 수 있는 방법은 무엇일까.

1. 부모 요소에 `padding: 1px`을 준다.
2. 부모 요소에 `border: 1px solid transparent`를 준다.
3. 부모 요소에 `overflow : hidden`을 준다.
4. 자식 요소에 `display: inline-block`로 준다.
5. 빈 요소를 넣는다.

---

[참고](https://www.youtube.com/watch?v=c19Mjg-ivxc&ab_channel=%EB%B9%94%EC%BA%A0%ED%94%84CSS)
