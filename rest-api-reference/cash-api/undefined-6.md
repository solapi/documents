# 결제

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/cash/v1/balance" %}
{% api-method-summary %}
결제
{% endapi-method-summary %}

{% api-method-description %}
paymentId 를 이용해 결제를 진행하고 금액을 충전합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="amount" type="number" required=true %}
충전\(결제\)할 금액입니다.
{% endapi-method-parameter %}

{% api-method-parameter name="paymentId" type="string" required=true %}
사용할 결제 수단에 대한 유니크한 값 입니다.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
정상적으로 결제가 된 경우
{% endapi-method-response-example-description %}

```javascript
{}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
paymentId 가 유효하지 않은 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidPaymentId"
    "errorMessage": "paymentId 가 유효하지 않습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=402 %}
{% api-method-response-example-description %}
돈이 부족해 결제가 취소된 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "BalanceInsufficient"
    "errorMessage": "보유 잔액이 부족합니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

