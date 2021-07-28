# 사이트에 OAuth2 토큰 설정

## Request

```text
POST https://api.solapi.com/appstore/v2/sso/connect-homepage
```

사이트에 OAuth2 토큰을 설정하기 위한 API입니다.   
API가 성공적으로 호출되었다면, 별도의 로그인 없이 사이트 이용이 가능합니다.

### Request Structure

```javascript
{
    "accessToken": "string"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| accessToken | `string` | true | OAuth2 엑세스 토큰 |
| returnUrl | `string` | optional | 해당 값이 있으면 작업이 끝난 후 해당 URL로 리다이렉트 됩니다. |

## Response

### Response Structure

```javascript
{
    "message": "success"
}
```

### Response Description

#### Response /

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| message | `string` | O | 결과 메시 |

## Samples

### 사이트에 OAuth2 토큰 설정

> **Sample Request**

```javascript
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZW1iZXJJZCI6Ik1FTVV3Z19HdkhFTXI0IiwiYWNjb3VudElkIjoiMjEwNzIyMTk2NTM4NjciLCJjbGllbnRJZCI6IkNJRE5VUklHT0NPT0xTTVMiLCJzY29wZSI6IioiLCJkb21haW4iOiJteXNpdGV0ZXN0MC5zb2xhcGkubmV0IiwiaXNXaGl0ZSI6ZmFsc2UsImlzQWRtaW4iOmZhbHNlLCJpYXQiOjE2MjcyMzIwNjYsImV4cCI6MTYyNzMxODQ2Nn0.f8U1VkTEWmE95-y7t2ynqxQw2omYhFKI4Zb5ZVjoFFF"     
}
```

> **Sample Response**

```javascript
{
    "message": "success"
}
```

