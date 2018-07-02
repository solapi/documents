---
description: 새로운 Micro Service Cash API 입니다.
---

# 잔액정보 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/cash/v1/balance" %}
{% api-method-summary %}
 잔액정보 조회
{% endapi-method-summary %}

{% api-method-description %}
현재 잔액정보를 조회합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "accountId": "4918201",
    "balance": 100,
    "isRecharging": false,
    "minimumCash": 0,
    "rechargeTo": 0,
    "rechargeTryCount": 0,
    "dateTriedRecharge": "2018-06-18T13:01:03.004Z",
    "dateCreated": "2018-06-18T13:01:03.004Z",
    "dateUpdated": "2018-06-20T14:04:05.030Z"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidAccountId",
    "errorMessage": "accountId 가 유효하지 않습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

