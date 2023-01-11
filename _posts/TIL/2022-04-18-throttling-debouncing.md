---
title: "Throttling & Debouncing"
excerpt: "이벤트의 실행 빈도를 줄여보자"

categories: javascript
tags: [javascript, throttling, debouncing]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### Debouncing

디바운싱이란 특정 시간이 지날 때 까지 반복이 일어나지 않고 대기하는 것이다. 연이은 이벤트 중에 마지막 이벤트만 인식한다.
대표적으로 검색기능을 구현할 때 사용한다.

### Throttling

쓰로틀링이란 연이어 발생한 이벤트에 일정한 딜레이를 포함 시켜서 연속적으로 발생하는 이벤트는 무시하는 방식이다. 스크롤 기능을 구현할 때 사용한다.
