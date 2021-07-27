# SSO 토큰 조회

## Request

```text
GET https://api.solapi.com/appstore/v2/sso/apps/:appId/customer-key/:customerKey
```

발급된 SSO Token을 앱 아이디와 사용자 구분 키로 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

### Path Parameters

| Name | Description |
| :---: | :---: |
| :appId | 앱 아이디 |
| :customerKey | 사용자 구분  |

## Response

### Response Structure

```javascript
{
    "customerKey": "string",
    "accountId": "string",
    "memberId": "string",
    "ssoToken": "string"
}
```

### Response Description

#### Response /

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| customerKey | `string` | true | 사용자 구분 키 |
| accountId | `string` | true | 계정 아이디  |
| memberId | `string` | true | 회원 아이디 |
| ssoToken | `string` | true | SSO 토큰 |

## Samples

### SSO 토큰 조

> **Sample Request**

```javascript
{}
```

> **Sample Response**

```javascript
{
    "customerKey": "customer001",
    "accountId": "1103225122",
    "memberId": "MEMWyGdnKfBsqq",
    "ssoToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhcHBJZCI6IkRvM2VOQ2ZvdUFCcSIsIm1lbWJlcklkIjoiTUVNVXdnX0d2SEVNcjQiLCJhY2NvdW50SWQiOiIyMTA3MjIxOTY1Mzg2NyIsImlhdCI6MTYyNzIyMjUxMn0.Eh_hXbqhfTC00QDvF4HrLgXnUqEsT80c6-r3qM6vFFF"
}
```

