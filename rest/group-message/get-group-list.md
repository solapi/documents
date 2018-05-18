## 그룹 목록
생성된 그룹목록을 리턴합니다.

### Resource URL
`https://solapi.com/GroupMessage/3/getGroupList`

### Request Syntax

```syntax
{
  "offset": Number,
  "limit": Number
}
```

### Required Parameters
필수 입력 사항이 없습니다.

### Optional Parameters
{% include "../fragments/offset.md" %}
{% include "../fragments/limit.md" %}

### Request Sample

{% codetabs name="CURL", type="curl" -%}
$ curl -X POST https://solapi.com/GroupMessage/3/getGroupList \
    --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]" \
    -d '{
      "offset": [OFFSET], 
      "limit": [LIMIT]
    }'
{%- language name="JavaScript", type="js" -%}
request(
  {
    url: "https://solapi.com/GroupMessage/3/getGroupList", //requset url
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]`
    },
    json: {
      "offset": [OFFSET],
      "limit": [LIMIT]
    }
  }
)
{%- language name="Python", type="py" -%}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/GroupMessage/3/getGroupList",
  json.dumps(
    {
      "offset": [OFFSET], 
      "limit": [LIMIT]
    }
  ),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]"})
conn.close()

{%- language name="PHP", type="php" -%}
<?php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/GroupMessage/3/getGroupList");
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
 'Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]'
));
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode(
  '{
    "offset": [OFFSET], 
    "limit": [LIMIT]
  }'
));
curl_exec($ch);
curl_close($ch);
?>
{%- endcodetabs %}

### Response Syntax

```syntax
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

### Response Sample

```json
{
    "offset": 0,
    "limit": 20,
    "groupList": {}
}
```

{%include "../fragments/totalCount.md" %}
{%include "../fragments/offset.md" %}
{%include "../fragments/limit.md" %}
{%include "../fragments/groupList.md" %}
{%include "../fragments/errors.md" %}
