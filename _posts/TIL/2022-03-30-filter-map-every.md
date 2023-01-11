---
title: "filter, map, every"
excerpt: "배열 메소드를 사용해보자"

categories: javascript
tags: [javascript, filter, map, every]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### Map

1.  Map : 배열의 원소를 일괄적으로 변형시킬 때 사용하기 좋음.

    - 사용 방법
      ![Untitled]![](https://images.velog.io/images/hyeun427/post/1679da96-cc92-45b7-8469-865b08ea47b2/map1.png)
      - map 안에 사용되는 item은 classmates의 원소들이 들어갈 파라미터이다. 네이밍은 원하는대로 하면 된다.
        <br />
    - 사용 예시
      - 요소로 이루어져있을 때
        ![](https://images.velog.io/images/hyeun427/post/9c95e375-3c32-4393-aa41-f32758c9e7f7/11.png)
        ![](https://images.velog.io/images/hyeun427/post/d2bc18ae-e4e4-40e6-87eb-26e5abd71bac/12.png)
      - 객체로 이루어져있을 때 - 객체를 의미하는 중괄호 빼먹지 않기!
        ![](https://images.velog.io/images/hyeun427/post/4febefc4-2703-4add-9faf-182aecd2ee16/13.png)
      - 실습 : 각 객체 요소에 school 추가! 쉼표로 구분하고 넣고싶은것 넣으면 됨.
        ![](https://images.velog.io/images/hyeun427/post/f2d54f0b-6f61-4472-935b-7f2cbb0e9b6d/14.png)
        ![](https://images.velog.io/images/hyeun427/post/bd7cc923-6e28-4425-9075-44354aa668f7/15.png)
        <br />
    - 용어 정리
      ![](https://images.velog.io/images/hyeun427/post/35125cb5-a319-41c0-9edc-cc843d4c6238/16.png)
    - 사용 팁

      - ![](https://images.velog.io/images/hyeun427/post/ac253c83-9f74-4647-af88-1cdf0f1be336/123.png)

      - 소괄호 생략에 관련된 예시 코드

        ```jsx
        const add = (aaa, bbb) => {
          return aaa + bbb;
        };

        add(1, 2);
        3;
        const add2 = (aaa, bbb) => aaa + bbb;

        const add3 = (aaa, bbb) => aaa + bbb;

        const classmates = [
          { name: "철수" },
          { name: "영희" },
          { name: "훈이" },
        ];

        classmates.map((el) => {
          name: el.name + "어린이";
        })(3)[(undefined, undefined, undefined)];
        ```

### Filter

2. Filter : 배열의 원소를 필터링 해주는 메서드. 원하는 원소만 도출해줌.
   - 사용 방법
     ![](https://images.velog.io/images/hyeun427/post/1ae249d7-f86e-4a66-9813-dbb0368b42b9/17.png)
   - 유의사항
     - map을 사용하면 기존 원소 갯수와 동일해야하고,
     - filter의 경우, 기존 원소 갯수보다 작거나 같아야한다. 더 많을 수 없다!
       ![](https://images.velog.io/images/hyeun427/post/bc7aed56-9d73-46ae-9aa2-a6f1efefbcba/18.png)

### every

3. every : 배열의 모든 원소가 조건에 맞는지 검사하는 메서드. 모든 원소가 조건을 만족하면 true, 하나라도 만족하지 않으면 false를 반환함.

   - 사용 방법

     ```
     // 화살표 함수
     every((element) => { ... } )
     every((element, index) => { ... } )
     every((element, index, array) => { ... } )

     // 콜백 함수
     every(callbackFn)
     every(callbackFn, thisArg)

     // 인라인 콜백 함수
     every(function callbackFn(element) { ... })
     every(function callbackFn(element, index) { ... })
     every(function callbackFn(element, index, array){ ... })
     every(function callbackFn(element, index, array) { ... }, thisArg)
     ```
