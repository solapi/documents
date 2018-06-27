---
description: 잔액 소진 알림을 설정할 수 있습니다.
---

# 잔액 소진 알림 설정

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/v1/balance/alert" %}
{% api-method-summary %}
Set Low Balance Alert
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-authenticated-account-id" type="string" required=true %}
사용자의 Account Id 입니다.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="balances" type="array" required=true %}
알림을 받을 잔액을 설정합니다.  
최대 3개까지 가능하고  
각 최소 20원 이상이여야 합니다.ㅅ
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 성공적으로 등록
{% endapi-method-response-example-description %}

```javascript
{
    "message": "성공적으로 수정되었습니다."
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
    "errorMessage": "child \"body\" fails because [child \"balances\" fails because [\"balances\" is required]]"
}

{
    "errorCode": "ValidationError",
    "errorMessage": "가격은 최소 1개, 최대 3개 입력 가능합니다."
}

{
    "errorCode": "ValidationError",
    "errorMessage": "설정 가능 최소 금액은 20원 입니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
로그인한 사용자가 아닐 경우
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



