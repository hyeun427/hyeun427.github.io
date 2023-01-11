---
title: "Pagination vs Infinite Scroll"
excerpt: "페이지 처리는 무엇으로 하면 좋을까"

categories: react
tags: [react, pagination, infinite scroll]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### Pagination

페이지네이션은 가지고 있는 데이터가 많아서 한 화면에 전부 보여줄 수 없는 경우에 사용한다. 흔히 게시판의 게시글 페이지 목록, 이전/다음페이지 기능을 생각하면된다.

![](https://media.vlpt.us/images/hyeun427/post/127bf80f-8a1e-44fa-aab8-a85054199eb7/image.png)

### Infinite Scroll

무한 스크롤은 사용자가 페이지 하단에 도달했을 때, 콘텐츠가 계속 로드되는 방식이다.
트위터나 인스타그램 같은 sns에서 우리가 접한 기능이다.

### Pagination vs Infinite Scroll

각 각의 장단점이 명확하기때문에 상황에 따라 선택해서 기능을 구현하면 될 것 이다.

페이지네이션의 장점은 사용자의 의도에 맞게 페이지를 넘길 수 있고 원하는 특정 항목의 위치를 파악해서 찾기 쉽다. 단점으로는 한 페이지에 제한된 내용만 확인할 수 있다는 점과 이전/다음 페이지 버튼을 누르고 새 페이지가 로드될 때까지 기다려야한다.

무한스크롤의 장점은 다양한 정보를 탐색할 수 있고, 모바일 환경에 적합하다. 다만 페이지 로딩 성능이 낮아질 수 있고 특정 항목을 검색하거나 그 위치로 되돌아오기 힘들다.
