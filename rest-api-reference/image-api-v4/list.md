---
description: 생성한 Image 목록을 조회합니다.
---

# 이미지 목록 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/images/v4/images" %}
{% api-method-summary %}
Get Image List
{% endapi-method-summary %}

{% api-method-description %}
Request 시에 parameter가 필요하지 않습니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

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

  


