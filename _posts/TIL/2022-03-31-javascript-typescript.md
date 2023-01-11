---
title: "Javascript와 Typescript"
excerpt: "Javascript와 Typescript의 차이는 무엇인가"

categories: javascript
tags: [javascript, typyscript]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## Javascript

Javascript

- HTML과 CSS로 만들어진 웹페이지를 동적으로 변경해주는 언어이다.
- 객체 기반의 스크립트 언어이다.
- 객체 지향형 프로그래밍과 함수형 프로그래밍 모두 표현할 수 있다.
- 확장자는 .js

## Typescript

Typescript

- MS에서 개발하고 관리하는 오픈소스 프로그래밍 언어이다.
- 자바스크립트의 상위 집합이다.
- 자바스크립트의 타입을 강제시키는 언어이다.
- 브라우저에서 직접 실행되지 않음 (Javascript로 컴파일 필요)
- 확장자는 .ts, .tsx

- 사용 방법

```
export default function TypescriptPage() {
	// 타입추론
	let aaa: String = "안녕하세요"
	aaa = 3

	// 타입명시
	let bbb: string = "반갑습니다"

	// 문자타입
	let ccc: string
	ccc = "반가워요!"
	ccc = 3

	// 숫자타입
	let ddd: number = 10
	ddd = "안뇽"

	// 불린타입
	let eee: boolean = true
	eee = false
	eee = "false" // true로 작동함

	// 배열타입
	// number[]는 number만 들어갈 수 있는 배열을 뜻한다.
	let fff: number[] = [1, 2, 3, 4, 5, "안녕하세여"]
	let ggg: string[] = ["철수", "영희", 13]
	// (number | string) []는 숫자나 문자열로 이루어진 배열이라는 의미로 ["철수", "영희", 13]이런 배열 가능해짐
	let hhh: (number | string)[] = [1, 2, 3, 4, 5, "안녕!"]

	// 객체타입
	// 객체에는 여러 타입이 들어갈 수 있기 때문에 명시해서 적어주어야 오류가 나지않는다.
	let profile1 = {
		name: "철수",
		age: 9,
		school: "다람쥐초등학교"
	}
	profile1.age = "아홉살" //처음 age의 타입이 넘버로 추론되어서 문자열은 들어갈 수 없다

	// 객체타입명시하기!
	interface IProfile2 {
		name: string
		age: string | number
		school: string
		hobby:
	}
	let profile2: IProfile2 = {
		name: "철수",
		age: 9,
		school: "다람쥐초등학교"
	}

	// 있어도 되고 없어도 되는 값을 적어주는 방법
	// hobby를 적어줘도 되고 안적어줘도 되는 값이라고 한다면 ?를 넣으면 된다. ?가 있으면 선택적, 없으면 필수적
	interface IProfile3 {
		name: string
		age: string | number
		school: string
		hobby?: string
	}
	let profile3: IProfile3 = {
		name: "철수",
		age: 9,
		school: "다람쥐초등학교"
	}

	// 함수 타입
	// 맨 마지막 string은 결과값의 타입을 정해준것.(return money1 + money2 + unit 이부분)
	const add = (money1: number, money2: number, unit: string): string => {
		return money1 + money2 + unit
	}
	const result = add(1000, 2000, "원")

	return <div>타입스크립트 연습하기!</div>
}
```

- **Javascript는 소규모 프로젝트에 사용하기 좋고, Typescript는 대규모 프로젝트에 적합하다!
  **
