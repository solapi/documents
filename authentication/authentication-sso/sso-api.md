# SSO 토큰으로 API 접근하기

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
[**API Documents**](https://docs.solapi.com/rest-api-reference/overview) ****를 통해 사용 가능한 API 를 확인할 수 있습니다.

