# 증빙자료 인증 요청

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/senderid/v1/papers/approval/{phoneNumber}" %}
{% api-method-summary %}
증빙자료 인증 요청
{% endapi-method-summary %}

{% api-method-description %}
등록된 발신번호의 인증을 위해 증빙자료를 제출 합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="phoneNumber" type="string" required=true %}
등록된 발신번호
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="documents" type="array" required=true %}
증빙자료로 제출할 문서 아이디
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

