---
title: "정규표현식"
excerpt: "이메일 검증과 핸드폰 번호 검증 어떻게 할래?"

categories: javascript
tags: [javascript, regular expression]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### Regular Expression 정규표현식

정규 표현식이란 문자열에서 특정 문자 조합을 찾기 위한 패턴이다. 정규표현식에서는 test 메서드를 사용할 수 있는데, 이 메서드를 사용하면 문자열에서 확인하고싶은 패턴을 검사해서 boolean으로 반환 시켜준다.

문법 구조는 아래와 같다.

```jsx
/정규표현식/.test("조건");
```

/ 사이에 정규표현식을 넣어서 작성하면 된다.

- 패턴을 만드는 조건이 있다.
  ![](https://velog.velcdn.com/images/hyeun427/post/ce316330-b3a1-443b-9538-4d3983d74ec9/image.png) 이미지 출처 : https://highcode.tistory.com/6

---

자주 사용하는 이메일 검증과 핸드폰 번호 검증하는 조건을 만들어보자.

우선 메일의 경우, 1) @ 앞은 문자 혹은 숫자가 하나 이상있어야하고, 2) 중간에는 @가 필수로 있어야하고, 3)@ 뒤는 문자 혹은 숫자가 하나 이상있고 .com 이 있어야한다.

1. @ 앞은 문자 혹은 숫자는 \w 를 작성하고 하나 이상 있어야하니까 + 를 추가해주면 될 것이다.
2. @은 필수이기 때문에 @을 그대로 작성한다.
3. @ 뒤는 문자 혹은 숫자는 \w 를 작성하고 하나 이상 있어야하니까 + 를 추가해준다. 그래도 . 이 있어야하는데 이때, 그냥 . 만 쓰게되면 정규표현식 조건에 의해 .이 의미하는 임의의 한 문자를 검증하게 되고 .이 아니더라도 다른 문자가 와도 true로 나오기때문에 .에 **\를 함께 써주어야** . 자체를 검증할 수 있다.
4. 시작과 끝에 각각 의미하는 ^와 $를 작성하면 완성이다.

```jsx
^\w+@\w+\.\w+$
```

<br>

---

<br>

다음은 핸드폰 번호 검증하는 경우이다. 핸드폰 번호는 01x-xxx(x)-xxxx의 구조를 가지고 있다.

-을 기준으로 앞부터 1,2,3 구역으로 생각해보자.

1. 우선 모든 구성은 숫자만 가능하다. 1번 구역의 숫자는 3자리가 필수이고 최대이다. 01까지는 동일하고 마지막 세번째 자리의 수는 0-9 사이의 수이다.
2. 2번 구역은 길이 범위가 3자리 혹은 4자리이고 구성하는 숫자는 0-9 사이의 수이다.
3. 3번 구역은 길이 범위가 4자리이고 구성하는 숫자는 0-9 사이의 수이다.
4. 시작과 끝에 각각 의미하는 ^와 $를 작성하면 완성이다.

```jsx
^01\d{1}-\d{3,4}-\d{4}$
```
