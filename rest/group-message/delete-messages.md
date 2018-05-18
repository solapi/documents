## 그룹메시지 삭제
그룹에 추가된 문자메시지를 삭제합니다.

### Resource URL
`https://solapi.com/GroupMessage/3/group/{groupId}/deleteMessages`

### Request Syntax

```syntax
{
  "messages": [
    {
      "messageId": "String"
    },
    ...
  ]
}
```

### Request Sample

{% codetabs name="CURL", type="curl" -%}
$ curl -X POST https://solapi.com/GroupMessage/3/group/[GROUP_ID]/deleteMessages \
    --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]" \
    -d '{
      "messages": [
        {
          "messageId": "[MESSAGE_ID]"
        }
      ]
    }'

{%- language name="JavaScript", type="js" -%}
request(
  {
    url: "https://solapi.com/GroupMessage/3/group/[GROUP_ID]/deleteMessages",
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]`
    },
    json: {
      "messages": [
        {
          "messageId": "[MESSAGE_ID]"
        }
      ]
    }
  }
)

{%- language name="Python", type="py" -%}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/GroupMessage/3/group/[GROUP_ID]/deleteMessages",
  json.dumps(
    {
      "messages": [
        {
          "messageId": "[MESSAGE_ID]"
        }
      ]
    }
  ),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]"})
conn.close()

{%- language name="PHP", type="php" -%}
<?php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/GroupMessage/3/group/[GROUP_ID]/deleteMessages");
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
 'Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]'
));
curl_setopt($ch, CURLOPT_POSTFIELDS, json.encode(
  '{
    "messages": [
      {
        "messageId": "[MESSAGE_ID]"
      }
    ]
  }'
));
curl_exec($ch);
curl_close($ch);
?>
{%- endcodetabs %}

### Required Parameters

messages
  - Array 형식의 삭제 요청할 메시지ID 목록
  - messageId
    - [메시지의 고유 ID](#)

### Optional Parameters
선택 옵션 사항이 없습니다.

### Limits
하나의 요청에 삭제 할 수 있는 메시지의 최대 갯수는 1,000 개를 넘을 수 없습니다.

### Response Syntax

```syntax
{
  "errorCount": Number,
  "resultList": [
    {
      "messageId": "String",
      "resultCode": "String"
    }
  ]
}
```

### Response Sample
```json
{
    "errorCount": 0,
    "resultList": [
        {
            "messageId": "MID1234567890",
            "resultCode": "Success"
        }
    ]
}
```
{% include "../fragments/errorCount.md" %}
* `resultList` - 요청한 건수만큼 결과를 반환합니다. 
{% include "../fragments/messageId.md" %}

### resultCode
  - 아래 코드 중 하나가 리턴됩니다.
    - `Success`
      - 성공
    - `MessageNotFound`
      - 메시지ID에 해당하는 메시지가 존재하지 않습니다.
    - `InternalError`
      - 내부 서부 오류로 인해 정상처리 되지 않았습니다.


{% include "../fragments/errors.md" %}
