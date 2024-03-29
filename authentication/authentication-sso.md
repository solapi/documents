# SSO 인증 방식

## SSO란?

싱글사인온\(Single Sign-On, SSO\)은 하나의 로그인 인증 수단을를 사용해 사이트에서 제공하는 여러 어플리케이션 혹은 API에 접근할 수 있는 중앙화된 세션 및 사용자 인증 서비스입니다.

솔라피에서도 SSO이용이 가능하며 기본 순서는 아래와 같습니다.

![](../.gitbook/assets/my-first-board.jpg)

각각 SSO API 관련 설명은 아래 링크를 참고해주세요.

\*\*\*\*[**SSO API Reference**](https://docs.solapi.com/api-reference/api-sso)  
****  
SSO 토큰, 홈페이지 토큰 모두 개별적으로 API 이용이 가능하며, 토큰을 이용하여 API접근 방식은 아래 링크를 참고해주세요.  
  
[**SSO 토큰 인증 방식**](https://docs.solapi.com/authentication/authentication-sso#sso-api)  
****[**홈페이지 토큰 인증 방식**](https://docs.solapi.com/authentication/oauth2-3/oauth2#step-3-api)  
  
기타 문의 사항은 [**1:1문의**](https://support.solapi.com/hc/ko/requests/new)로 남겨주시면 감사하겠습니다.  
  
REST API를 요청\(Request\)할 때 HTTP 헤더에 SSO Authorization 정보를 추가하여 인증 받을 수 있습니다. API를 요청한 계정의 소유자를 확인하는데 필수적인 절차입니다.  
  
SSO 인증을 이용할 시 [**SSO 전용 토큰을 발급**](https://docs.solapi.com/api-reference/api-sso) 받아야 하며,  
앱 관리자가 허용한 IP에서만 해당 인증방식을 사용 가능합니다.



## SSO 토큰을 사용하여 API 접근하기

발급 받은 SSO 토큰을 사용하여 아래와 같이 솔라피의 API를 이용할 수 있습니다.

```text
curl -X (GET|POST) https://api.solapi.com/<접근하려는 API url>
-H 'Authorization: sso <SSO Token>'
```

위의 예제처럼 요청하려는 HTTP Request 의 Header 에 Authorization 값을 넣어주면 됩니다.  
예를 들어 요청하려는 API 가 간단한 유저 정보를 가져오는 API 라고 한다면 아래와 같이 할 수 있습니다.

```text
curl -X GET https://api.solapi.com/users/v1/member
-H 'authorization: sso eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhcHBJZCI6IkRvM2VOQ2ZvdUFCcSIsIm1lbWJlcklkIjoiTUVNVXdnX0d2SEVNcjQiLCJhY2NvdW50SWQiOiIyMTA3MjIxOTY1Mzg2NyIsImlhdCI6MTYyNzIyMjUxMn0.Eh_hXbqhfTC00QDvF4HrLgXnUqEsT80c6-r3qM6vfff'
```

정상적으로 결과가 온다면 해당 멤버 정보 데이터를 가져 왔을 것 입니다.  
[API Documents](https://docs.solapi.com/rest-api-reference/overview) 를 통해 사용 가능한 API 를 확인할 수 있습니다.



