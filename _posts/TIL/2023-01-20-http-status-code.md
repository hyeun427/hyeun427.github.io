---
title: "HTTP 상태 코드 정리"
excerpt: "에러 보고싶지 않아.."

categories: network
tags: [http]

toc: true
toc_sticky: true

author_profile: true
sidebar: false
---

## HTTP 상태 코드

클라이언트가 서버에 작업 요청을 하면 서버는 그 작업의 수행 결과를 응답한다. 이 떄 HTTP 상태 코드를 사용해서 작업의 성공 여부를 알려준다.
http 상태 코드는 각 상황에 맞게 표준으로 정해져있고 첫번째 숫자에 따라 구분할 수 있다.

## 100번 대 informational response(조건부 응답)

전송 프로토콜 수준의 정보 교환

### 100 Continue(계속)

이 임시적인 응답은 지금까지의 상태가 괜찮으며 클라이언트가 계속해서 요청을 하거나 이미 요청을 완료한 경우에는 무시해도 되는 것을 알려준다.

### 101 Switching Protocol(프로토콜 전환)

이 코드는 클라이언트가 보낸 Upgrade 요청 헤더에 대한 응답에 들어가며 서버에서 프로토콜을 변경할 것임을 알려준다.

### 102 Processing (처리, WebDAV)

이 코드는 서버가 요청을 수신하였으며 이를 처리하고 있지만, 아직 제대로 된 응답을 알려줄 수 없음을 알려준다.

### 103 Early Hints (사전 도움)

이 상태 코드는 주로 Link 헤더와 함께 사용되어 서버가 응답을 준비하는 동안 사용자 에이전트가(user agent) 사전 로딩(preloading)을 시작할 수 있도록 한다.

## 200번 대 Success(성공)

클라이언트 요청이 성공적으로 수행

### 200 OK(성공)

요청이 성공적으로 되었습니다. 성공의 의미는 HTTP 메서드에 따라 달라진다
GET: 리소스를 불러와서 메시지 바디에 전송됐다.
HEAD: 개체 해더가 메시지 바디에 있다.
PUT 또는 POST: 수행 결과에 대한 리소스가 메시지 바디에 전송됐다.
DELETE: 삭제를 수행했고 응답 메시지가 이후의 상태를 설명한다.
TRACE: 메시지 바디는 서버에서 수신한 요청 메시지를 포함하고 있다.

### 201 Created(작성됨)

요청이 성공적이었으며 그 결과로 새로운 리소스가 생성됐다. 이 응답은 일반적으로 POST 요청 또는 일부 PUT 요청 이후에 따라온다.

### 202 Accepted(허용됨)

요청을 수신하였지만 그에 응하여 행동할 수 없다. 이 응답은 요청 처리에 대한 결과를 이후에 HTTP로 비동기 응답을 보내는 것에 대해서 명확하게 명시하지 않는다. 이것은 다른 프로세스에서 처리 또는 서버가 요청을 다루고 있거나 배치 프로세스를 하고 있는 경우를 위해 만들어졌다.
즉, 서버가 요청을 접수했지만 아직 처리하지 않았다.

### 203 Non-Authoritative Information(신뢰할 수 없는 정보)

이 응답 코드는 돌려받은 메타 정보 세트가 오리진 서버의 것과 일치하지 않지만 로컬이나 서드 파티 복사본에서 모아졌음을 의미한다. 이러한 조건에서는 이 응답이 아니라 200 OK 응답을 반드시 우선된다.

### 204 No Content(내용 없음)

요청에 대해서 보내줄 수 있는 콘텐츠가 없지만, 헤더는 의미있을 수 있다. 사용자-에이전트는 리소스가 캐시 된 헤더를 새로운 것으로 업데이트할 수 있다.

## 300번 대 Redirection(리다이렉션, 경로 재지정)

클라이언트가 요청을 완료하기 위해 추가 조취를 취해야 함

### 301 Moved Permanently(영구적 이동)

이 응답 코드는 요청한 리소스의 URI가 변경되었음을 의미한다. 새로운 URI가 응답에서 아마도 주어질 수 있다.

### 304 Not Modified(변경 없음)

이것은 캐시를 목적으로 사용된다. 이것은 클라이언트에게 응답이 수정되지 않았음을 알려주며, 그러므로 클라이언트는 계속해서 응답의 캐시 된 버전을 사용할 수 있다.

## 400번 대 Client Error(클라이언트 오류)

클라이언트로 인한 오류 발생

### 400 Bad Request(잘못된 요청)

이 응답은 잘못된 문법으로 인하여 서버가 요청을 이해할 수 없음을 의미한다.

### 401 Unauthorized(권한 없음)

비록 HTTP 표준에서는 "미승인(unauthorized)"를 명확히 하고 있지만, 의미상 이 응답은 "비인증(unauthenticated)"을 의미한다. 클라이언트는 요청한 응답을 받기 위해서는 반드시 스스로를 인증해야 한다. 로그인을 실패한 경우 또는 로그인하지 않는 사용자가 회원의 기능을 사용하려 할 때 사용한다.

### 403 Forbidden(접근 금지)

클라이언트가 콘텐츠에 접근할 권리를 가지고 있지 않다. 예를들어 회원이 로그인을 한 상태이지만 아직 결제를 하지 않아 Netflix를 이용할 수 없는 경우이다. 401과 다른 점은 서버가 클라이언트가 누구인지 알고 있다.

### 404 Not Found(찾을 수 없음)

서버가 요청받은 리소스를 찾을 수 없다. 브라우저에서는 알려지지 않은 URL을 의미한다. 이것은 API에서 종점(URI)은 적절하지만 리소스 자체는 존재하지 않음을 의미할 수도 있다. 서버들은 인증받지 않은 클라이언트로부터 리소스를 숨기기 위하여 이 응답을 403 대신에 전송할 수도 있다. 이 응답 코드는 웹에서 반복적으로 발생하기 때문에 가장 유명할지도 모른다.

### 405 Method Not Allowed(허용되지 않은 메서드)

요청에 지정된 메서드가 URI로 표시된 리소스에 허용되지 않음을 의미한다.
이는 클라이언트가 문서 조회만 제공하는 컬렉션에 POST, PUT 또는 DELETE를 전송해 컬렉션을 변경하려고 하는 경우일 수 있다.

### 408 Request Timeout(요청 시간 초과)

이 응답은 요청을 한지 시간이 오래된 연결에 일부 서버가 전송하며, 어떨 때에는 이전에 클라이언트로부터 어떠한 요청이 없었다고 하더라도 보내지기도 합니다. 이것은 서버가 사용되지 않는 연결을 끊고 싶어 한다는 것을 의미한다. 이 응답은 특정 몇몇 브라우저에서 빈번하게 보이는데, Chrome, Firefox 27+, 또는 IE9와 같은 웹서핑 속도를 올리기 위해 HTTP 사전 연결 메커니즘을 사용하는 브라우저들이 해당된다. 또한, 일부 서버는 이 메시지를 보내지 않고 연결을 끊어버리기도 한다.

## 500번 대 Server Error(서버 오류)

서버로 인한 오류 발생

### 500(내부 서버 오류)

서버에 오류가 발생하여 요청을 수행할 수 없다.

### 501(구현되지 않음)

서버에 요청을 수행할 수 있는 기능이 없다. 예를 들어 서버가 요청 메소드를 인식하지 못할 때 이 코드를 표시한다.

### 502 (Bad Gateway, 불량 게이트웨이)

서버가 게이트웨이나 프록시 역할을 하고 있거나 또는 업스트림 서버에서 잘못된 응답을 받았다.

### 503(서비스를 사용할 수 없음)

서버가 오버로드되었거나 유지관리를 위해 다운되었기 때문에 현재 서버를 사용할 수 없다. 이는 대개 일시적인 상태이다.

### 504(게이트웨이 시간초과)

서버가 게이트웨이나 프록시 역할을 하고 있거나 또는 업스트림 서버에서 제때 요청을 받지 못했다.

---

[참고](https://developer.mozilla.org/ko/docs/Web/HTTP/Status)
[참고](https://ko.wikipedia.org/wiki/HTTP_%EC%83%81%ED%83%9C_%EC%BD%94%EB%93%9C)
