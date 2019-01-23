---
description: 잔액 소진 알림의 on/off 를 설정합니다.
---

# 잔액 소진 알림 on/off 설정

{% api-method method="put" host="https://rest.coolsms.co.kr" path="/cash/v1/balance/alert/power" %}
{% api-method-summary %}
Set Low Balance Alert Power
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="enabled" type="boolean" required=true %}
설정의 on/off 를 입력받습니다.  
true or false
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
정상적으로 수정완료
{% endapi-method-response-example-description %}

```javascript
{
    "accountId": "12925149",
    "enabled": true
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
    "errorMessage": "[['enabled' must be a boolean]]"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

