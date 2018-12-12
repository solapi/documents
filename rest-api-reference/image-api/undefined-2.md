# 이미지 정보 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/images/v4/images/{imageId}" %}
{% api-method-summary %}
이미지 정보 조회
{% endapi-method-summary %}

{% api-method-description %}
이미지 아이디를 사용해 이미지 정보를 조회합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="imageId" type="string" required=true %}
이미지 아이디
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "imageId": "imageId",
    "file": {
        "name": "file name",
        "size": 1234
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
해당 이미지가 자신의 것이 아닌 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "Forbidden",
    "errorMessage": "자신의 이미지만 조회할 수 있습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
해당 이미지 아이디가 존재하지 않는 경우
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



