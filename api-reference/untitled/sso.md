# SSO 토큰 발급

## Request

```text
POST https://api.solapi.com/appstore/v2/sso/connect
```

SSO 토큰 발급을 위한 API입니다.   
이미 가입된 회원일 경우 토큰 생성 후 토큰 값을 리턴 하게 되며,  
새로운 회원일 경우 회원 가입 후 토큰 값이 리턴 됩니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

### Request Structure

```javascript
{
    "appId": "string",
    "email": "string",
    "password": "string",
    "customerKey": "string"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| appId | `string` | true | SSO 토큰 발급을 위한 앱 아이디 |
| email | `string` | true | 사용할 이메일 주소 |
| password | `string` | true | 비밀번호 |
| customerKey | `string` | true | 앱 관리자가 구분 가능한 사용자 구분 키 |

## Response

### Response Structure

```javascript
{
    "ssoToken": "string"
}
```

### Response Description

#### Response /

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| ssoToken | `string` | O | SSO 토큰 |

## Samples

### SSO 토큰 발급

> **Sample Request**

```javascript
{
  "appId": "Y04mh1xXdFFf",
  "email": "test@gmail.com",
  "password": "test@1234",
  "customKey": "customer001"  
}
```

> **Sample Response**

```javascript
{
    "ssoToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhcHBJZCI6IkRvM2VOQ2ZvdUFCcSIsIm1lbWJlcklkIjoiTUVNVXdnX0d2SEVNcjQiLCJhY2NvdW50SWQiOiIyMTA3MjIxOTY1Mzg2NyIsImlhdCI6MTYyNzIyMjUxMn0.Eh_hXbqhfTC00QDvF4HrLgXnUqEsT80c6-r3qM6FFFo"
}
```

