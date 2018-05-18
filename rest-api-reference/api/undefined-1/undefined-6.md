# 그룹메시지 목록

그룹에 추가된 문자메시지 목록을 조회합니다.

## Resource URL

`https://solapi.com/GroupMessage/3/group/{groupId}/getMessageList`

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

$ curl -X POST [https://solapi.com/GroupMessage/3/group/\[GROUP\_ID\]/getMessageList](https://solapi.com/GroupMessage/3/group/[GROUP_ID]/getMessageList)  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"  -d '{ "offset": 0, "limit": 20 }'

request\( { url: "[https://solapi.com/GroupMessage/3/group/\[GROUP\_ID\]/getMessageList](https://solapi.com/GroupMessage/3/group/[GROUP_ID]/getMessageList)", method: 'post', headers: { 'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE]}, Salt=[UNIQID], Signature=[SIGNATURE]` }, json: { "offset": 0, "limit": 20 } } \)

conn = HTTPSConnection\('solapi.com', '443'\) conn.request\( "POST", "/GroupMessage/3/group/\[GROUP\_ID\]/getMessageList", json.dumps\( { "offset": 0, "limit": 2 } \), {"Authorization":"HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"}\) conn.close\(\)

&lt;?php $ch = curl\_init\(\); curl\_setopt\($ch, CURLOPT\_URL,"[https://solapi.com/GroupMessage/3/group/\[GROUP\_ID\]/getMessageList](https://solapi.com/GroupMessage/3/group/[GROUP_ID]/getMessageList)"\); curl\_setopt\($ch, CURLOPT\_POST, 1\); curl\_setopt\($ch, CURLOPT\_HTTPHEADER, array\( 'Authorization: HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]' \)\); curl\_setopt\($ch, CURLOPT\_POSTFIELDS, json.encode\( '{ "offset": 0, "limit": 20 }' \)\); curl\_exec\($ch\); curl\_close\($ch\); ?&gt;

## Response Syntax

```text
{
  "totalCount": Number,
  "offset": Number,
  "limit": Number,
  "messageList": {
    "messageId": {
      "to": "String",
      "from": "String",
      "country": "String",
      "type": "String",
      "text": "String",
      "scheduledDate": "String",
      "statusCode": "String"
    },
    ...
  }
}
```

## Response Sample

```javascript
{
    "totalCount": 1,
    "offset": 0,
    "limit": 20,
    "messageList": {
        "M3V20170911170756D7DOS9AARGNB6BG": {
            "to": "01000000001",
            "from": "0212345678",
            "text": "테스트 문자",
            "type": "SMS",
            "statusCode": "2000"
        }
    }
}
```

