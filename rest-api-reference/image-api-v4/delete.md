# 이미지 삭제

{% api-method method="delete" host="https://rest.coolsms.co.kr" path="/images/v4/images/:imageId" %}
{% api-method-summary %}
Delete Image
{% endapi-method-summary %}

{% api-method-description %}
이미지 아이디를 이용해 이미지를 삭제합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="imageId" type="string" required=true %}
이미지마다 가지고 있는 고유한 아이디입니다.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
삭제가 성공한 경
{% endapi-method-response-example-description %}

```javascript
{
    "result": "SUCCESS"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
이미지를 찾지 못한경
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ImageNotFound",
    "errorMessage": "이미지 아이디를 다시 확인해주세요."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



