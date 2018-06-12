---
description: 등록된 결제 수단으로 결제된 목록을 조회합니다.
---

# 결제 수단 목록 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/cash/v1/payment" %}
{% api-method-summary %}
Get Payment List
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-Authenticated-Account-Id" type="string" required=true %}
결제 수단 목록을 조회할 유저의 accountId 입니다.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
성공적으로 목록을 가져온 경우
{% endapi-method-response-example-description %}

```javascript
{
    "_id": "xxxxxx",
    "payments": [
        {
            "autoRecharge": false,
            "description": "월급 받는 카드 1",
            "_id": "6010864779767788001528419340229"
        },
        {
            "autoRecharge": false,
            "description": "월급 받는 카드 1",
            "_id": "6011201322422313001528419340229"
        }
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
파라미터 오류
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidAccountId",
    "errorMessage": "Account ID가 유효하지 않습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



