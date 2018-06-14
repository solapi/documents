# 결제 수단 등록

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/cash/v1/payment" %}
{% api-method-summary %}
결제 수단 등록
{% endapi-method-summary %}

{% api-method-description %}
웹에서 발급받은 고객키를 등록합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="description" type="string" required=true %}
해당 카드에 대한 설명
{% endapi-method-parameter %}

{% api-method-parameter name="customerId" type="string" required=true %}
Stripe 에서 발급받은 customer Id
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
정상적으로 등록된 경우
{% endapi-method-response-example-description %}

```javascript
{}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}
이미 등록된 카드인 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "CardAlreadyExists",
    "errorMessage": "중복된 별칭이 있거나 이미 등록된 카드입니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



