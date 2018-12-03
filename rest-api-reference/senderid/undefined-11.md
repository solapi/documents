# 문서 정보 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/senderid/v1/documents/{documentId}" %}
{% api-method-summary %}
문서 정보 조회
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "documentid": "doc20181030105615mmxdst163symmx4",
  "accountid": "12925149",
  "name": "hprnmur6une3fs6.png",
  "url": "https://coolsms-sender-id-test.s3.ap-northeast-2.amazonaws.com/temp/hprnmur6une3fs6.png",
  "originalname": "hprnmur6une3fs6.png",
  "datecreated": "2018-11-20t07:36:51.859z",
  "category": "SENDERID_APPROVAL",
  "use": false
}
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



