---
title: "Shallow Routing"
excerpt: "next에 대해 살짝 알아보자"

categories: next
tags: [next, shallow routing]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

Shallow Routing은 데이터를 가져오는 메소드를 다시 동작시키지 않고 url을 변경할 수 있게 해준다.

Shallow Routing을 사용하려면 아래와 같이 작성하면 된다.

```jsx
import { useEffect } from "react";
import { useRouter } from "next/router";

// Current URL is '/'
function Page() {
  const router = useRouter();

  useEffect(() => {
    // Always do navigations after the first render
    router.push("/?counter=10", undefined, { shallow: true });
  }, []);

  useEffect(() => {
    // The counter changed!
  }, [router.query.counter]);
}

export default Page;
```

shallow의 옵션을 true로 하면 url만 변경하면 알아서 리렌더링이 된다!
