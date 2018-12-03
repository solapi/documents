# 활성화된 발신번호 목록 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/senderid/v1/numbers/active" %}
{% api-method-summary %}
활성화된 발신번호 목록 조회
{% endapi-method-summary %}

{% api-method-description %}
현재 활성화되어 있는 발신번호로만 구성된 목록을 가져옵니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
    '01000000000',
    '01000000001'
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



