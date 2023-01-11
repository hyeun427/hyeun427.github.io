---
title: "얕은 복사와 깊은 복사"
excerpt: "어떤 복사가 원본과 복사본의 값이 모두 바뀔까?!"

categories: react
tags: [react, shallow copy, deep copy]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

### Shallow Copy

얕은 복사는 주소값을 복사한다.
그렇기 때문에 원본의 값이 변하면 복사본의 값도 변하고, 복사본의 값이 변하면 원본의 값도 변하게 된다. 이미지로 확인하면 쉽게 이해할 수 있다.

<p align=center><img src="https://media.vlpt.us/images/hyeun427/post/1c3afadf-9c57-4737-bdca-1c6fb4814d4a/%EC%96%95%EC%9D%80%EB%B3%B5%EC%82%AC.png" width=100px></p>

- 코드로 알아보자.

<p align=center><img src = "https://media.vlpt.us/images/hyeun427/post/ae38383e-3ce1-457b-8068-5f774bbe01ae/%EC%96%95%EC%9D%80%EB%B3%B5%EC%82%AC%EC%98%88%EC%8B%9C.png" width= 300px></p>

obj1을 복사하여 obj2에 넣었다. 얕은 복사 개념에 따라 값을 넣었다기보다 그 값의 주소를 공유한다고 이해하면 된다. 그렇기 때문에 obj2.a 값을 100으로 바꾸어도 obj1.a의 값도 같이 100으로 바뀌는 것!

---

### Deep Copy

깊은 복사란 아예 새로운 객체안 속성(property)만 복사해서 넣어주는 것이다. 얕은 복사와 달리 새로운 주소를 가지기때문에 원본 값과 복사본 값은 서로에게 영향을 줄 수 없다.

- 코드로 알아보자

<p align=center><img src="https://media.vlpt.us/images/hyeun427/post/8b9a5882-6e93-41a0-b87d-265d4e8f061b/image.png" width= 300px></p>

obj1을 스프레드연산자(...)를 사용하여 obj2에 넣었다. 깊은 복사 개념에 따라 새로운 주소에 새로운 객체를 만든 것이다. 그렇기 때문에 obj2.a 값을 100으로 바꾸면 obj1.a의 값은 변경사항이 없기때문에 그대로 1, obj2.a 값만 100으로 출력되는 것을 확인할 수 있다.

---

- 깊은 복사는 1 depth만 가능하기때문에 그 이상의 복사는 어렵다. 완벽히 깊은 복사를 하고 싶다면 JSON.parse()와 JSON.stringify()함수를 사용하면 가능하다.

<p align=center><img src="https://media.vlpt.us/images/hyeun427/post/8e4d2c34-8dcc-45b3-a005-ac3231485181/image.png" height= 300px></p>
