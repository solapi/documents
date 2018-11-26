# 문서 업로드

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/senderid/v1/documents" %}
{% api-method-summary %}
문서 업로드
{% endapi-method-summary %}

{% api-method-description %}
인증,  발신번호 개수 증가, 중복해제 요청을 위한 문서를 업로드 합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="file" type="string" required=true %}
업로드할 파일 base64 endcoding 된 문자열  
\(pdf, jpg, gif, png, tif 지원\)
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
파일 이름
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

