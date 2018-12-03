# 발신번호 개수 증가 요청

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/senderid/v1/papers/limitation" %}
{% api-method-summary %}
발신번호 개수 증가 요청
{% endapi-method-summary %}

{% api-method-description %}
발신번호 개수를 더 사용할 수 있도록 관리자에게 요청합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="documents" type="string" required=true %}
문서 아이디
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="boolean" required=true %}
변경을 원하는 발신번호 개수
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
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
  "limitationDocuments": [
    {
      "documents": [ "DOC201811201547359TEOYN5B3NIGPAU" ],
      "reason": null,
      "status": "PENDING",
      "dateCreated": "2018-11-20T06:47:34.608Z",
      "dateUpdated": "2018-11-20T06:47:34.608Z",
      "limitationId": "LID20181120154735OY58OVC5ALA8SOM",
      "limitRequested": 10,
      "limitBeforeRequest": 2
    }
  ],
  "senderIds": [
    {
      "unlockDuplicate": {
        "duplicateId": null,
        "reason": null,
        "reasonForRequested": null,
        "name": null,
        "status": null,
        "dateCreated": null,
        "dateUpdated": null
      },
      "status": "ACTIVE",
      "expireAt": null,
      "method": "ARS",
      "dateCreated": "2018-11-20T05:25:27.285Z",
      "dateUpdated": "2018-11-20T05:25:27.285Z",
      "log": [
        {
          "createAt": "2018-11-20T05:25:27.755Z",
          "message": "인증수단 'ARS'로 발신번호 인증이 완료되었습니다."
        }
      ],
      "approvalDocuments": [],
      "phoneNumber": "01000000000",
      "handleKey": "SED20181120142527G9MUYZKJXEV6ADY"
    }
  ]
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
},
{
    "errorCode": "InvalidDocumentId",
    "errorMessage": "등록된 문서 정보를 찾을 수 없습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



