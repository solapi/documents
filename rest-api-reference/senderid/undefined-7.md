# 발신번호 개수 증가 요청

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/senderid/v1/papers/limitation" %}
{% api-method-summary %}
발신번호 개수 증가 요청
{% endapi-method-summary %}

{% api-method-description %}
발신번호 개수를 더 사용할 수 있도록 관리자에게 요청합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="documents" type="string" required=true %}
문서 아이디
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="boolean" required=true %}
변경을 원하는 발신번호 개수
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

