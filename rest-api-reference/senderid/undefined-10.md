# 문서 목록 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/senderid/v1/documents" %}
{% api-method-summary %}
문서 목록 조회
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

{% api-method-query-parameters %}
{% api-method-parameter name="documentId" type="string" required=false %}
문서 아이디
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="string" required=false %}
ISO 8601 형식의 검색 시작 날짜
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="string" required=false %}
ISO 8601 형식의 검색 마지막 날짜
{% endapi-method-parameter %}

{% api-method-parameter name="startKey" type="string" %}
검색 시작 키
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" %}
조회할 데이터 수
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
"data": {
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
},
"nextKey": "DOC20181030105615MMXDST163SYMMX6"
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



