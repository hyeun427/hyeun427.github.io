---
title: "파일을 불러오거나 내보내려면 어떻게 해야할까"
excerpt: "import와 export를 사용해보자"

categories: react
tags: [javascript, react, import, export]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## 모듈

- 모듈이란 하나의 파일이다. 즉, 스크립트 하나는 모듈 하나이다.

## Import

- import문은 다른 모듈에서 내보낸 바인딩을 가져올 때 사용한다.
  사용법은 아래와 같다. 반드시 모듈의 경로를 설정해주어야한다.

```
import { 가져오고 싶은 항목 } from '파일명'
```

## Export

- export문은 JavaScript 모듈에서 함수, 객체, 원시 값을 내보낼 떄 사용한다. 이때 내보낸 값은 import문으로 가져가 사용할 수 있다.

- export에는 Named exports와 Default exports 두가지 방법이있다.

#### Named exports

- Named exports는 여러값을 export 하는데 유용하다.

#### Default exports

- 모듈 당 딱 한 개의 default export만 있어야 한다.
- 가장 간단하게 export 할 수 있으며, 딱 한개만 default export를 할 수 있기 때문에, "메인" 이라고 할 수 있는 것을 default export 하는 것이 좋다.
