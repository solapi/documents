# 홈페이지 토큰 발급

## Request

```text
GET https://api.solapi.com/appstore/v2/sso/issue-hompage-token
```

홈페이지 토큰 발급을 위한 API입니다.   
기존 인증 방식으론 사용할 수 없으며, SSO 인증을 통해 사용 가능합니다.  
앱 관리자에 의해 허용된 IP로만 접근 가능합니다.  
발급된 홈페이지 토큰은 다른 API 접근을 위해 사용될 수 있으며, 따로 사이트에 토큰 설정을 하기 위해 사용될 수 있습니다.

### SSO Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

### Request Structure

```javascript
{}
```

## Response

### Response Structure

```javascript
{
    "homepageToken": "string"
}
```

### Response Description

#### Response /

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| homepageToken | `string` | O | 홈페이지 토큰 |

## Samples

### 홈페이지 토큰 발급

> **Sample Request**

```javascript
{}
```

> **Sample Response**

```javascript
{
    "homepageToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZW1iZXJJZCI6Ik1FTVV3Z19HdkhFTXI0IiwiYWNjb3VudElkIjoiMjEwNzIyMTk2NTM4NjciLCJjbGllbnRJZCI6IkNJRE5VUklHT0NPT0xTTVMiLCJzY29wZSI6IioiLCJkb21haW4iOiJteXNpdGV0ZXN0MC5zb2xhcGkubmV0IiwiaXNXaGl0ZSI6ZmFsc2UsImlzQWRtaW4iOmZhbHNlLCJpYXQiOjE2MjczNjg1NjksImV4cCI6MTYyNzQ1NDk2OX0.apDT3yMWy1jx-rT0CxcsO_eI9gsQCSqYx9jPBN44FFF"
}
```

