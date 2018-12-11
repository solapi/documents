# 이미지 생성

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/images/v4/images" %}
{% api-method-summary %}
이미지 생성
{% endapi-method-summary %}

{% api-method-description %}
base64 로 인코딩 된 문자열을 이용해서 이미지를 등록합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="image" type="string" required=true %}
등록할 이미지 base64 endcoding 된 문자열
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    imageId: "imageIdExample"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



