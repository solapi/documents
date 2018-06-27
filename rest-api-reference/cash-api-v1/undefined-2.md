---
description: 유저들이 설정한 잔액 소진 알림 리스트를 조회합니다.
---

# 잔액 소진 알림 리스트 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/v1/admin/balance/alert" %}
{% api-method-summary %}
Get Low Balance Alert List
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-is-admin" type="boolean" required=true %}
관리자임을 증명하는 헤더 입니다.  
True여야 성공적으로 증명됩니다.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="accountId" type="string" required=false %}
조회할 유저의 accountId 입니다.  
넣지 않을 시 전체 조회를 의미합니다.
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="string" %}
조회를 시작할 위치 입니다.  
\(default: 0\)
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="boolean" %}
조회를 할 갯수 입니다.  
\(default: 20\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
성공적으로 조회
{% endapi-method-response-example-description %}

```javascript
[
    {
        "balances": [
            "20",
            "4000",
            "60000"
        ],
        "_id": "12925149",
        "dateCreated": "2018-06-26T07:20:58.731Z",
        "dateUpdated": "2018-06-26T07:20:58.757Z"
    }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
관리자임을 증명하지 못한 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "Forbidden",
    "errorMessage": "잘못된 접근입니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



