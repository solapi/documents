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
{% api-method-query-parameters %}
{% api-method-parameter type="string" name="accountId" required=true %}
조회할 계정의 accountId 입니다.
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="number" required=false %}
검색을 시작할 번호입니다.  
default: 0
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" %}
검색할 갯수 입니다.  
default: 20
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
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
    "errorCode": "ValidationError",
    "errorMessage": "child \"query\" fails because [child \"paymentId\" fails because [\"paymentId\" is required]]"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



