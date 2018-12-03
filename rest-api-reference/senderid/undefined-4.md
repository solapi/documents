# 발신번호 삭제

{% api-method method="delete" host="https://rest.coolsms.co.kr" path="/senderid/v1/numbers/{phoneNumber}" %}
{% api-method-summary %}
발신번호 삭제
{% endapi-method-summary %}

{% api-method-description %}
'ACTIVE' 상태가 아닌 발신번호를 삭제합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="phoneNumber" type="string" required=true %}
발신번호
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

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
{
  "accountId": "12925149",
  "dateCreated": "2018-11-20T05:25:27.757Z",
  "dateUpdated": "2018-11-20T05:25:27.757Z",
  "limit": 2,
  "limitationDocuments": [],
  "senderIds": []
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidSenderId",
    "errorMessage": "등록된 발신번호 정보를 찾을 수 없습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "FailedToDelete",
    "errorMessage": "'ACTIVE'상태의 발신번호는 삭제가 불가능합니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



