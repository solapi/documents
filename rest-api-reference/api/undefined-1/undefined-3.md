# 그룹 목록

생성된 그룹목록을 리턴합니다.

## Resource URL

`https://solapi.com/GroupMessage/3/getGroupList`

## Request Syntax

```text
{
  "offset": Number,
  "limit": Number
}
```

## Required Parameters

필수 입력 사항이 없습니다.

## Optional Parameters

## Request Sample

$ curl -X POST [https://solapi.com/GroupMessage/3/getGroupList](https://solapi.com/GroupMessage/3/getGroupList)  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[SALT\], Signature=\[SIGNATURE\]"  -d '{ "offset": \[OFFSET\], "limit": \[LIMIT\] }'

request\( { url: "[https://solapi.com/GroupMessage/3/getGroupList](https://solapi.com/GroupMessage/3/getGroupList)", //requset url method: 'post', headers: { 'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]` }, json: { "offset": \[OFFSET\], "limit": \[LIMIT\] } } \)

conn = HTTPSConnection\('solapi.com', '443'\) conn.request\( "POST", "/GroupMessage/3/getGroupList", json.dumps\( { "offset": \[OFFSET\], "limit": \[LIMIT\] } \), {"Authorization":"HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"}\) conn.close\(\)

&lt;?php $ch = curl\_init\(\); curl\_setopt\($ch, CURLOPT\_URL,"[https://solapi.com/GroupMessage/3/getGroupList](https://solapi.com/GroupMessage/3/getGroupList)"\); curl\_setopt\($ch, CURLOPT\_POST, 1\); curl\_setopt\($ch, CURLOPT\_HTTPHEADER, array\( 'Authorization: HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]' \)\); curl\_setopt\($ch, CURLOPT\_POSTFIELDS, json\_encode\( '{ "offset": \[OFFSET\], "limit": \[LIMIT\] }' \)\); curl\_exec\($ch\); curl\_close\($ch\); ?&gt;

## Response Syntax

```text
{
  "totalCount": Number,
  "offset": Number,
  "limit": Number,
  "groupList": {
    "groupId": {
      "groupOptions": {
        "appId": "String",
        "appVersion": "String",
        "mode": "String",
        "forceSms": "String",
        "onlyAta": "String",
        "osPlatform": "String",
        "devLanguage": "String",
        "sdkVersion": "String",
        "apiVersion": "String"
      },
      "count": {
        "sms": Number,
        "lms": Number,
        "mms": Number,
        "ata": Number,
        "cta": Number,
        "push": Number
      },
      "price": {
        "unitPrice": {
          "sms": Number,
          "lms": Number,
          "mms": Number,
          "ata": Number,
          "cta": Number,
          "push": Number
        },
        "calculatedPrice": {
          "sms": Number,
          "lms": Number,
          "mms": Number,
          "ata": Number,
          "cta": Number,
          "push": Number,
          "total": Number
        }
      }
    },
    ...
  }
}
```

## Response Sample

```javascript
{
    "offset": 0,
    "limit": 20,
    "groupList": {}
}
```

