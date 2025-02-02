---
title: "실행 컨텍스트"
excerpt: "실행 컨텍스트에 대한 불친절한 나만의 정리"

categories: javascript
tags: [javascript, Execution Context]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## 실행 컨텍스트

### 실행 컨텍스트란 무엇인가

식별자를 등록하고 관리하는 스코프와 코드 실행 순서 관리를 구현한 내부 메커니즘으로, 모든 코드는 실행 컨텍스트를 통해 실행되고 관리된다. 실행 컨텍스트는 실행 컨텍스트 스택과 렉시컬 환경으로 구성되어 있다.

렉시컬 환경은 식별자와 스코프를 기록하고 관리하는데, 키와 값을 갖는 객체 형태의 스코프를 생성하여 식별자를 키로 등록하고 식별자에 바인딩된 값을 관리한다. 실행 컨텍스트 스택은 Last In First Out 구조로 코드 실행 순서를 관리한다.

소스코드는 '소스코드 평가'와 '소스코드 실행', 두 과정으로 나뉘어 처리된다. 평가 과정에서 실행 컨택스트를 생성하고, 선언문을 먼저 실행해 식별자를 키로 실행 컨텍스트가 관리하는 스코프에 등록한다. 평가 과정이 끝나면 선언문을 제외한 소스코드가 순차적으로 실행되는데 (런타임), 필요한 변수나 함수의 참조는 실행 컨텍스트가 관리하는 스코프에서 검색해 취득한다.

자바스크립트 엔진은 먼저 전역 코드를 평가하여 전역 실행 컨텍스트를 생성하고, 함수가 호출되면 함수 코드를 평가하여 함수 실행 컨텍스트를 생성한다. 실행 컨텍스트는 실행컨텍스트 스택에서 추가되고 제거된다. 실행 컨텍스트 스택은 코드의 실행 순서를 관리하는데, 최상위에 있는 실행 컨텍스트가 현재 실행 중인 코드의 실행 컨텍스트이다.

#### 한줄 정리

- 실행 컨텍스트는 소스코드를 실행하기 위해 필요한 환경을 제공하고 코드의 실행 결과를 실제로 관리하는 영역을 말한다. scope, hoisting, this, function, closure 등의 동작원리를 담고 있는 자바스크립트의 핵심원리이다.

---

### Lexical Environment과 Variable Environment의 차이

- Lexical Environment이란 변수 및 함수 등의 식별자와 외부 참조에 관한 정보를 가지고 있는 컴포넌트이다. Variable Environment는 Lexical Environment와 동일한 성격을 띠지만 var로 선언된 변수만 저장한다는 점에서 다르다.

#### 한줄 정리

- Lexical Environment는 var로 선언된 변수를 제외하고 나머지(let 으로 선언되었거나 함수 선언문)를 저장하고, Variable Environment는 var로 선언된 변수만 저장한다는 점에서 다르다.

> **참고 및 출처**
> 모던자바스크립트 deep dive 23장 실행 컨텍스트
