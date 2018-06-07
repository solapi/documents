---
description: 등록된 결제 수단을 삭제합니다.
---

# 결제 수단 삭제

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/cash/v1/payment" %}
{% api-method-summary %}
Delete Payment
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-Authenticated-Account-Id" type="string" required=true %}
결제 수단을 삭제할 유저의 accountId 입니다.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="paymentId" type="string" required=true %}
등록되어있는 결제 수단의 id 입니다.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
성공적으로 삭제
{% endapi-method-response-example-description %}

```javascript
{
    "message": "성공적으로 삭제되었습니다.",
    "paymentId": "9013662849992081001528356492111"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
필수 파라미터 미입력
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ValidationError",
    "errorMessage": "child \"body\" fails because [child \"paymentId\" fails because [\"paymentId\" is required]]"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
없는 paymentId 입력 시
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ResourceNotFound",
    "errorMessage": "결제 수단을 찾지 못했습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



