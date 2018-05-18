## 그룹 생성
메세지를 담을 그룹을 생성하여 그룹아이디를 리턴합니다.
생성된 그룹은 24시간 후에 자동 삭제됩니다.

### Resource URL
`https://solapi.com/GroupMessage/3/createGroup`

### Request Syntax

```syntax
{
  "groupOptions": {
    "appId": "String",
    "appVersion": "String",
    "testMode": "String",
    "forceSms": "String",
    "osPlatform": "String",
    "devLanguage": "String",
    "sdkVersion": "String",
    "scheduledDate": "Date"
  }
}
```


### Request Sample
{% codetabs name="CURL", type="curl" -%}
$ curl -X POST https://solapi.com/GroupMessage/3/createGroup \
    --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[ISO 8601 DATE], Salt=[UNIQID], Signature=[SIGNATURE]" \
    -d '{
          "groupOptions": { }
      }'
{%- language name="JavaScript", type="js" -%}
request(
  {
    url: "https://solapi.com/GroupMessage/3/createGroup",
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]`
    },
    json: {
      "groupOptions" : {
      }
    }
  }
)
{%- language name="Python", type="py" -%}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/GroupMessage/3/createGroup",
  json.dumps(
    {
      "groupOptions" : {}
    }
  ),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]"})
conn.close()
{%- language name="PHP", type="php" -%}
<?php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/GroupMessage/3/createGroup"); //requset URL
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATA], Salt=[SALT], Signature=[SIGNATURE])');
curl_setopt($ch, CURLOPT_POSTFIELDS, json.encode(
  '{
    "groupOptions" : { }
  }'
));
curl_exec($ch);
curl_close($ch);
?>
{%- endcodetabs %}


### Required Parameters
필수 입력 사항이 없습니다.

### Optional Parameters

{% include "../fragments/groupOptions.md" %}



### Response Syntax

```syntax
{
  "groupId": "String",
  "groupOptions": {
    "appId": "String",
    "appVersion": "String",
    "testMode": "String",
    "forceSms": "String",
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
    "push": Number,
    "total": Number
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
  },
  "ttl": Number
}
```

### Response Sample

```json
{
  "groupId":"G3V201709120949522NDJEIWYLRGVCUK",
  "groupOptions":
  {
    "appId":"null",
    "appVersion":"null",
    "apiVersion":"3",
    "forceSms":"false",
    "onlyAta":"false",
    "osPlatform":"null",
    "devLanguage":"null",
    "sdkVersion":"null"
  },
  "count":
  {
    "sms":0,
    "lms":0,
    "mms":0,
    "ata":0,
    "cta":0,
    "push":0
  },
  "price":
  {
    "unitPrice":
    {
      "sms":20,
      "lms":50,
      "mms":200,
      "ata":15,
      "cta":20,
      "push":5
    },
    "calculatedPrice":
    {
      "sms":0,
      "lms":0,
      "mms":0,
      "ata":0,
      "cta":0,
      "push":0,
      "total":0
    }
  },
  "ttl":7200
}
```

### Optional Parameters
{% include "../fragments/groupOptions.md" %}
{% include "../fragments/price.md" %}
{% include "../fragments/ttl.md" %}
{% include "../fragments/errors.md" %}