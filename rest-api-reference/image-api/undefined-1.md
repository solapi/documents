# 이미지 목록 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/images/v4/images" %}
{% api-method-summary %}
이미지 목록 조회
{% endapi-method-summary %}

{% api-method-description %}
자신이 등록한 이미지들의 목록을 불러올 수 있습니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
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
[
    {
        "file": { "name": "TEST", size: 10 },
        "delflag": false,
        "accountId": "12925149",
        "dateCreated": "2018-06-08T07:47:53.848Z",
        "dateUpdated": "2018-06-08T07:47:53.848Z",
        "imageId": 'image Id'
    }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

  


