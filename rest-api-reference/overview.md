# Overview



쿨에스엠에스의 REST API Reference 내용을 담고 있습니다.

_참고_ REST는 Representational State Transfer의 약자로 API 연동 규격을 명확하게 정의되고 쉽게 구현 할 수 있습니다. [https://ko.wikipedia.org/wiki/REST](https://ko.wikipedia.org/wiki/REST)

쿨에스엠에스 SMS REST API 서버로 Request를 보내기 위해서 인증을 거쳐야 합니다.  
[API Key 를 이용한 방법](../authentication/api-key.md)과 소셜로그인으로 불리우는 [OAuth 2.0](../authentication/oauth2.md) 을 지원하고 있습니다.

## Resource URL 구성

`https://rest.coolsms.co.kr/<ServiceName>/<Version>/<ResourcePath>`

`<ServiceName>`

* [Message API v4](message-api-v4/)
* [Image API](image-api/)

`<Version>`

* 서비스 버전

`<ResourcePath>`

* 필요시 특정 리소스 경로를 나타냅니다

## API 요청

API Request 시 파라메터 값과 Response 의 데이터 값은 JSON 형식으로 합니다. 모든 Request 에 Content-type 을 application/json 으로 설정하여 주세요.

## 오류 핸들링

Response 의 HTTP Status Code 값이 200 일 때 API 는 정상적으로 호출되었고 Response 의 Body 에 적절한 데이터가 리턴됩니다.

HTTP Status Code 200 이외의 값의 경우 오류로써 보통의 경우 errorCode 와 errorMessage 이 함께 리턴됩니다. 각 API 마다 정의된 오류코드는 다르지만 공통적으로 리턴될 수 있는 코드는 [Message Status Codes](message-status-codes.md) 를 참고하세요.





