## 그룹메시지 추가
그룹에 발송할 메시지를 추가합니다.

### Resource URL
`https://solapi.com/GroupMessage/3/group/{groupId}/addMessages`

### Request Syntax

```syntax
{
  "messages": [
    {
      "to": { /* required */
        "recipient": "String",
        "recipients": [
          "String",
          ...
        ],
        "recipientsWithCustomFields": [
          {
            "recipient": "String",
            "customFields": {
              "myMessageId": "String",  /* 사용자 정의 필드 */
              "mySequence": Number,     /* 사용자 정의 필드 */
              ...
            }
          },
        ],
      },
      "from": "String", /* required */
      "text": "String", /* required */
      "type": "String",
      "country": "String",
      "subject": "String",
      "imageId": "String",
      "kakaoOptions": {
        "senderKey": "String",
        "templateCode": "String",
        "buttonName": "String",
        "buttonUrl": "String",
        "disableSms": "Boolean"
      }
    },
    ...
  ],
}
```

### Request Sample

{% codetabs name="CURL", type="curl" -%}
$ curl -X POST  https://solapi.com/GroupMessage/3/group/[GROUP_ID]/addMessages \
    --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATRUE]" \
    -d '{
      "messages": [
        {
          "to": {
            "recipient": "[RECIPIENT]"
          },
          "from": "[FROM]",
          "text": "[TEXT]",
          "type":"[TYPE]"
        }
      ]
    }'
{%- language name="JavaScript", type="js" -%}
request(
  {
    url: "https://solapi.com/GroupMessage/3/group/[GROUP_ID]/addMessages",
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]`
    },
    json: {
      "messages": [
        {
          "to": {
            "recipient": "[RECIPIENT]"
          },
          "from": "[FROM]",
          "text": "[TEXT]",
          "type": "[TYPE]"
        }
      ]
    }
  }
)
{%- language name="Python", type="py" -%}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/GroupMessage/3/group/[GROUP_ID]/addMessages",
  json.dumps(
    {
      "messages": [
        {
          "to": {
            "recipient": "[RECIPIENT]"
          },
          "from": "[FROM]",
          "text": "[TEXT]",
          "type":"[TYPE]"
        }
      ]
    }
  ),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]"})
conn.close()
{%- language name="PHP", type="php" -%}
<?php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/GroupMessage/3/group/[GROUP_ID]/addMessages");
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
 'Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]'
));
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode(
  '{
    "messages": [
      {
        "to": {
          "recipient": "[RECIPIENT]"
        },
        "from": "[FROM]",
        "text": "[TEXT]",
        "type":"[TYPE]"
      }
    ]
  }'
);
curl_exec($ch);
curl_close($ch);
?>
{%- endcodetabs %}


### Required Parameters

messages
  - Array 형식의 메시지 발송 정보
{% include "../fragments/to.md" %}
{% include "../fragments/from.md" %}
{% include "../fragments/text.md" %}

### Optional Parameters

messages
  - Array 형식의 메시지 발송 정보
{%include "../fragments/type.md" %}
{% include "../fragments/country.md" %}
  - subject
    - type이 LMS, MMS 일 때 제목
{% include "../fragments/imageId.md" %}
{% include "../fragments/kakaoOptions.md" %}

### Limits
그룹메시지 추가 API에 다음 3가지 제한사항이 있습니다.

  - 요청의 총 데이터 크기는 10MB를 넘을 수 없습니다.
  - 한번의 요청(Request)에 대해 수신번호는 1,000 개를 넘을 수 없습니다.
  - 하나의 그룹에 담을 수 있는 메시지는 1,000,000 개 입니다.


### Response Syntax

```syntax
{
  "errorCount": Number,
  "resultList": [
    {
      "recipient": "String",
      "messageId": "String",
      "type": "String",
      "statusCode": "String",
      "customFields": {
        ...
      }
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
            "recipient": "01000000001",
            "messageId": "M3V20170911164820TCBLKDEWPAO8VOK",
            "type": "SMS",
            "statusCode": "2000"
        }
    ]
}
```

{% include "../fragments/errorCount.md" %}
{% include "../fragments/resultList.md" %}
{% include "../fragments/messageResultList.md" %}
{% include "../fragments/errors.md" %}
  - RecipientsTooMany
    - 입력된 수신번호가 1000개를 넘음
    - HTTP Status Code: 413


