# 잔액 출금

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/cash/v1/withdraw" %}
{% api-method-summary %}
잔액 출금
{% endapi-method-summary %}

{% api-method-description %}
보유하고 있는 잔액을 출금 신청합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="holderName" type="string" required=true %}
예금주 성함
{% endapi-method-parameter %}

{% api-method-parameter name="bankCode" type="string" required=true %}
은행 코드
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="number" required=true %}
출금할 금액
{% endapi-method-parameter %}

{% api-method-parameter name="accountNumber" type="string" required=true %}
계좌 번호
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
출금이 정상적으로 된 경우
{% endapi-method-response-example-description %}

```javascript
{
    "status": "SUCCESS"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
서버에서 요청을 거부한 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ValidationError",
    "errorMessage": "금액은 양의 정수만 입력 가능합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
서버에서 요청을 거부한 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "Forbidden",
    "errorMessage": "보유하신 금액이 부족합니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



