# 문서 삭제

{% api-method method="delete" host="https://rest.coolsms.co.kr" path="/senderid/v1/documents" %}
{% api-method-summary %}
문서 삭제
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="documents" type="string" required=true %}
문서 아이디
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
  {
    "documentId": "DOC20181030105615MMXDST163SYMMX4",
    "accountId": "12925149",
    "name": "hPrnmUR6UNE3fS6.png",
    "url": "https://coolsms-sender-id-test.s3.ap-northeast-2.amazonaws.com/temp/hPrnmUR6UNE3fS6.png",
    "originalName": "hPrnmUR6UNE3fS6.png",
    "dateCreated": "2018-11-20T07:36:51.859Z",
    "category": "SENDERID_APPROVAL",
    "use": false
  },
  {
    "documentId": "DOC20181030105615MMXDST163SYMMX5",
    "accountId": "12925149",
    "name": "kcIkooNqo52MUnl.png",
    "url": "https://coolsms-sender-id-test.s3.ap-northeast-2.amazonaws.com/temp/kcIkooNqo52MUnl.png",
    "originalName": "kcIkooNqo52MUnl.png",
    "dateCreated": "2018-11-20T07:36:51.865Z",
    "category": "SENDERID_APPROVAL",
    "use": false
  }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidDocumentId",
    "errorMessage": "등록된 문서 정보를 찾을 수 없습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



