# 증빙자료 인증 요청

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/senderid/v1/papers/approval/{phoneNumber}" %}
{% api-method-summary %}
증빙자료 인증 요청
{% endapi-method-summary %}

{% api-method-description %}
등록된 발신번호의 인증을 위해 증빙자료를 제출 합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="phoneNumber" type="string" required=true %}
등록된 발신번호
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="documents" type="array" required=true %}
증빙자료로 제출할 문서 아이디
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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
      "status": "PENDING",
      "expireAt": null,
      "method": null,
      "dateCreated": "2018-11-20T05:25:27.285Z",
      "dateUpdated": "2018-11-20T05:25:27.285Z",
      "log": [
        {
          "createAt": "2018-11-20T05:25:27.755Z",
          "message": "발신번호를 생성하였습니다."
        }
      ],
      "approvalDocuments": [
        {
          "documents": [ "DOC20181030105615MMXDST163SYMMX3" ],
          "status": "PENDING",
          "reason": null,
          "dateCreated": "2018-11-21T02:46:38.586Z",
          "dateUpdated": "2018-11-21T02:46:38.586Z",
          "approvalId": "APD20181121114638RULY1TKWG7ACESI"
        }
      ],
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



