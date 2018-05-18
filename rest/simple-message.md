# 심플메시지

1,000건 이하의 소량의 문자메시지를 발송합니다. 대량의 문자메시지를 안정적으로 발송하려면 [그룹메시지](#GroupMessage) 을 사용하세요.


## Resource URL

`https://solapi.com/SimpleMessage/3/sendMessages`

## Request Syntax

```json
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
                "myCustomField": {Map} | [Array] | "String" | Number,  /* 사용자 정의 필드 */
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
    "groupOptions": {
      "appId": "String",
      "appVersion": "String",
      "mode": "String",
      "forceSms": "String",
      "onlyAta": "String",
      "osPlatform": "String",
      "devLanguage": "String",
      "sdkVersion": "String",
      "scheduledDate": "Date"
    }
  }
```

### Required Parameters

* `messages` - [Array] 형식의 메시지 발송 정보
  {% include "./fragments/to.md" %}
  {% include "./fragments/from.md" %}
  {% include "./fragments/text.md" %}

### Optional Parameters

* `messages` - [Array] 형식의 메시지 발송 정보
  {% include "./fragments/type.md" %}
  {% include "./fragments/country.md" %}
  {% include "./fragments/subject.md" %}
  {% include "./fragments/imageId.md" %}
  {% include "./fragments/scheduledDate.md" %}
  {% include "./fragments/kakaoOptions.md" %}
{% include "./fragments/groupOptions.md" %}

## Sample Request

{% codetabs name="CURL", type="bash" -%}
$ curl -X POST https://solapi.com/SimpleMessage/3/sendMessages \
    --header "Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]" \
    -d '{
          "messages": [
            {
              "to": {"recipient": "01000000001"},
              "from": "0212345678",
              "text": "테스트 문자",
              "type": "SMS"
            }
          ], "options": { }
        }'
{%- language name="JavaScript", type="javascript" -%}
request(
  {
    url: "https://solapi.com/SimpleMessage/3/sendMessages",
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]`
    },
    json: {
      "messages": [
        {
          "to": {"recipient": "01000000001"},
          "from": "0212345678",
          "text": "테스트 문자",
          "type": "SMS"
        }
      ], "options": { }
    }
  }
)
{%- language name="Python", type="python" -%}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/SimpleMessage/3/sendMessages",
  json.dumps(
    {
      "messages": [
        {
          "to": {"recipient": "01000000001"},
          "from": "0212345678",
          "text": "테스트 문자",
          "type": "SMS"
        }
      ], "options": { }
    }
  ),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]"})
conn.close()
{%- language name="PHP", type="php" -%}
<?php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/SimpleMessage/3/sendMessages"); //requset URL
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATA], Salt=[SALT], Signature=[SIGNATURE])');
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode(
    {
      "messages": [
        {
          "to": {"recipient": "01000000001"},
          "from": "0212345678",
          "text": "테스트 문자",
          "type": "SMS"
        }
      ], "options": { }
    }
));
curl_exec($ch);
curl_close($ch);
?>
{%- endcodetabs %}

## Limits

메시지발송 API에서 하나의 요청에 대해 아래와 같은 두가지 제한사항이 있습니다.

  - 하나의 요청의 총 데이터 크기는 10MB를 넘을 수 없습니다.
  - 하나의 요청에 대해 수신번호는 1,000개를 넘을 수 없습니다.

## Response Syntax

```json
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
    ],
  }
```

* `errorCount` - 오류 카운트
* `resultList` - Array 형식의 결과 목록
  {% include "./fragments/recipient.md" %}
  {% include "./fragments/messageId.md" %}
  {% include "./fragments/type.response.md" %}
  {% include "./fragments/statusCode.md" %}
  {% include "./fragments/customFields.md" %}
  
## Sample Response

```json
  {
    "errorCount": 1,
    "resultList": [
      {
        "recipient": "01000000001",
        "messageId": "MID58E73E3A9AAB5",
        "type": "SMS",
        "resultCode": "2000"
      },
      {
        "recipient": "01000000002",
        "messageId": "MID58E8AE3A3BAB3",
        "type": "SMS",
        "resultCode": "2000"
      },
      {
        "recipient": "01000000003",
        "messageId": "MID58E8AA4B4CBC4",
        "type": "SMS",
        "resultCode": "2000"
      },
      {
        "recipient": "01000000004",
        "messageId": "MID58B8A34B43A01",
        "type": "SMS",
        "resultCode": "2000",
        "customFields": {
          "mySequence": 1
        }
      },
      {
        "recipient": "01000000004",
        "messageId": "MID58BCB129CD38B",
        "type": "SMS",
        "resultCode": "1026", // 수신번호 중복
        "customFields": {
          "mySequence": 2
        }
      },
      {
        "recipient": "01000000005",
        "messageId": "MID58E82E312B384",
        "type": "SMS",
        "resultCode": "2000",
        "customFields": {
          "mySequence": 3
        }
      }
    ]
  }
```

## Errors

아래의 오류가 리턴될 수도 있습니다.

**NotEnoughBalance**

  잔액이 부족합니다.

  HTTP Status Code: 402

**NothingToSend**

  보낼 메시지가 없습니다.

  HTTP Status Code: 404

공통적으로 일어날 수 있는 오류 코드를 확인하시려면 [오류코드](errors.md) 를 참고하세요.
